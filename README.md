# ime_jellyfish
Docker image for the Jellyfish kmer counting software

## Prerequisities

In order to run this container you'll need docker installed.

* [Windows](https://docs.docker.com/windows/started)
* [OS X](https://docs.docker.com/mac/started/)
* [Linux](https://docs.docker.com/linux/started/)

## Usage

The docker image provides the [Jellyfish](https://github.com/gmarcais/Jellyfish) tool. It will run the `jellyfish` command as entrypoint.
Therefore, running a container is as easy as:

```
docker run --rm greatfireball/ime_jellyfish --version
```

Just provide all required parameters via command line.
Default working directory is `/data`.
Therefore, input data should be mounted using `/data` volume.

Running the command to count kmers for a local file `reads.fasta` in the current folder:

```
docker run --user $(id -u):$(id -g) --rm -v $PWD:/data greatfireball/ime_jellyfish count -m 21 -s 100M -t 10 -C reads.fasta
```
Quoting from the [Wiki](https://github.com/gmarcais/Jellyfish/tree/master/doc#counting-all-k-mers):
> "This will count canonical (-C) 21-mers (-m 21), using a hash with 100 million elements (-s 100M) and 10 threads (-t 10) in the sequences in the file reads.fasta. The output is written in the file mer counts.jf by default (change with -o switch)."

## Releases

The master branch contains a rolling release.
The develop branch is used for further development.
Specific tags are used for different Jellyfish releases. Latest release is [![](https://images.microbadger.com/badges/version/greatfireball/ime_jellyfish:v2.2.10.svg)](https://microbadger.com/images/greatfireball/ime_jellyfish:v2.2.10 "Get your own version badge on microbadger.com").

| Version/Branch | Commit in Docker Repo | Image |
| -------------- | --------------------- | ----- |
| [![](https://images.microbadger.com/badges/version/greatfireball/ime_jellyfish:master.svg)](https://microbadger.com/images/greatfireball/ime_jellyfish:master "Get your own version badge on microbadger.com") | [![](https://images.microbadger.com/badges/commit/greatfireball/ime_jellyfish:master.svg)](https://microbadger.com/images/greatfireball/ime_jellyfish:master "Get your own commit badge on microbadger.com") | [![](https://images.microbadger.com/badges/image/greatfireball/ime_jellyfish:master.svg)](https://microbadger.com/images/greatfireball/ime_jellyfish:master "Get your own image badge on microbadger.com") |
| [![](https://images.microbadger.com/badges/version/greatfireball/ime_jellyfish:develop.svg)](https://microbadger.com/images/greatfireball/ime_jellyfish:develop "Get your own version badge on microbadger.com") | [![](https://images.microbadger.com/badges/commit/greatfireball/ime_jellyfish:develop.svg)](https://microbadger.com/images/greatfireball/ime_jellyfish:develop "Get your own commit badge on microbadger.com") | [![](https://images.microbadger.com/badges/image/greatfireball/ime_jellyfish:develop.svg)](https://microbadger.com/images/greatfireball/ime_jellyfish:develop "Get your own image badge on microbadger.com") |
| [![](https://images.microbadger.com/badges/version/greatfireball/ime_jellyfish:v2.2.10.svg)](https://microbadger.com/images/greatfireball/ime_jellyfish:v2.2.10 "Get your own version badge on microbadger.com") | [![](https://images.microbadger.com/badges/commit/greatfireball/ime_jellyfish:v2.2.10.svg)](https://microbadger.com/images/greatfireball/ime_jellyfish:v2.2.10 "Get your own commit badge on microbadger.com") | [![](https://images.microbadger.com/badges/image/greatfireball/ime_jellyfish:v2.2.10.svg)](https://microbadger.com/images/greatfireball/ime_jellyfish:v2.2.10 "Get your own image badge on microbadger.com") |
| [![](https://images.microbadger.com/badges/version/greatfireball/ime_jellyfish:v1.1.12.svg)](https://microbadger.com/images/greatfireball/ime_jellyfish:v1.1.12 "Get your own version badge on microbadger.com") | [![](https://images.microbadger.com/badges/commit/greatfireball/ime_jellyfish:v1.1.12.svg)](https://microbadger.com/images/greatfireball/ime_jellyfish:v1.1.12 "Get your own commit badge on microbadger.com") | [![](https://images.microbadger.com/badges/image/greatfireball/ime_jellyfish:v1.1.12.svg)](https://microbadger.com/images/greatfireball/ime_jellyfish:v1.1.12 "Get your own image badge on microbadger.com") |

## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

## Author

- **Frank Förster** - *Initial work* - [greatfireball](https://github.com/greatfireball)

See also the list of [contributors](https://github.com/greatfireball/ime_seqfilter/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
