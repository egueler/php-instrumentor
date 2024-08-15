Original is [here](https://github.com/ovanr/webFuzz/tree/v1.2.0/instrumentor).
This is not meant as a release or be usable by anyone. It's a quick and dirty php instrumentor extracted from webfuzz and adjusted a bit to dump the code coverage to a log file, it was used for some fuzzing evaluation purposes for the Atropos paper, [see here](https://github.com/CISPA-SysSec/atropos-legacy). It's only released so the evaluation docker builds can access it from GitHub.

Here is the original README:

# PHP-INSTRUMENTOR

Instrument PHP files using Node, Edge, Node-Edge (combo) or Path coverage policy.

Coverage feedback can be outputted in the form of a file or via HTTP headers.

## Usage

**Tested on PHP8.2.3**

1. Install needed libraries using composer:
```sh
composer install
```

2. Start instrumenting using:
```sh
php src/instrumentor.php --verbose --method (file|http) --policy (node|edge|...) --exclude exclude.txt --dir <root-of-webapp>
```

You can pass in a file to exclude which is a line separated list of paths 
that should not be instrumented.
If a folder name is provided then the contents of the whole folder will not
be instrumented

3. Create instrumentation output folder and update permissions:
```sh
sudo mkdir /var/instr
sudo chmod o+rwx /var/instr
```

## Authors

* **Orpheas van Rooij** - *orpheas.vanrooij@outlook.com*

## License

[GNU GPLv3](https://choosealicense.com/licenses/gpl-3.0/)
