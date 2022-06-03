# Dependancy Hashing

Modified: 2022-05

Generate a unique md5 hash for a subset of version controlled dependancy files. This has application in building base images where the images can be tagged with a hash of all version controlled application dependancy files. This provides an elegant way to solve dependancy conflicts across multiple concurrent development source branches. Credit to [kschinkel](https://github.com/kschinkel) for the idea.

> `md5sum` is used to hash input files. `man md5sum` for more information on the `md5sum` utility

## Usage
This script is meant for programmatic use so stdout printouts are kept to a minimum. To `dephash` two dependancy files `requirements.txt` and `apt-packages.txt`:
```bash
./dephash -f requirements.txt -f apt-packages.txt
```

To execute remotely:
```bash
wget -O - https://raw.githubusercontent.com/ztnel/dephash/master/dephash | bash -s -- -f requirements.txt -f apt-packages.txt
```

## License
This repository is licensed under the terms of the [MIT License](LICENSE)