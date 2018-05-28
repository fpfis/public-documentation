---
date: 2018-20-05T10:21:05+02:00
title: phpDoc
tags: [ composer, documentation ]
---

This plugins allows for generating [phpDocumentator](https://phpdoc.org/) site based on `phpdoc.xml`

## Example

```
pipeline:
  build-doc:
    image: phpdrone/phpdoc:2.8
```

## Result

```
Collecting files .. OK
Initializing parser .. OK
Parsing files
Parsing /drone/src/github.com/phpdrone/drone-plugin-sdk/src/Repo.php
  No summary was found for this file
  No summary for method getOwner()
  No summary for method getName()
  No summary for method getLink()
  No summary for method getDefaultBranch()
  No summary for method isPrivate()
  No summary for method isTrusted()
Parsing /drone/src/github.com/phpdrone/drone-plugin-sdk/src/Commit.php
  No summary was found for this file
  No summary for method getBranch()
  No summary for method getTag()
  No summary for method getSha()
  No summary for method getMessage()
  No summary for method getAuthorName()
  No summary for method getAuthorEmail()
  No summary for method getRef()
Parsing /drone/src/github.com/phpdrone/drone-plugin-sdk/src/Build.php

Warning: count(): Parameter must be an array or an object that implements Countable in /root/.composer/vendor/phpdocumentor/phpdocumentor/src/phpDocumentor/Plugin/Core/Descriptor/Validator/Constraints/Functions/IsArgumentInDocBlockValidator.php on line 33

Warning: count(): Parameter must be an array or an object that implements Countable in /root/.composer/vendor/phpdocumentor/phpdocumentor/src/phpDocumentor/Plugin/Core/Descriptor/Validator/Constraints/Functions/IsArgumentInDocBlockValidator.php on line 33

Warning: count(): Parameter must be an array or an object that implements Countable in /root/.composer/vendor/phpdocumentor/phpdocumentor/src/phpDocumentor/Plugin/Core/Descriptor/Validator/Constraints/Functions/IsArgumentInDocBlockValidator.php on line 33

Warning: count(): Parameter must be an array or an object that implements Countable in /root/.composer/vendor/phpdocumentor/phpdocumentor/src/phpDocumentor/Plugin/Core/Descriptor/Validator/Constraints/Functions/IsArgumentInDocBlockValidator.php on line 33
  No summary was found for this file
Storing cache in "/drone/src/github.com/phpdrone/drone-plugin-sdk/doc" .. OK
Load cache                                                         ..    0.008s
Preparing template "clean"                                         ..    0.017s
Preparing 17 transformations                                       ..    0.000s
Build "elements" index                                             ..    0.000s
Replace textual FQCNs with object aliases                          ..    0.002s
Resolve @link and @see tags in descriptions                        ..    0.001s
Enriches inline example tags with their sources                    ..    0.000s
Build "packages" index                                             ..    0.002s
Build "namespaces" index and add namespaces to "elements"          ..    0.000s
Collect all markers embedded in tags                               ..    0.000s
Transform analyzed project into artifacts                          .. 
Applying 17 transformations
  Initialize writer "phpDocumentor\Plugin\Core\Transformer\Writer\FileIo"
  Initialize writer "phpDocumentor\Plugin\Twig\Writer\Twig"
  Initialize writer "phpDocumentor\Plugin\Graphs\Writer\Graph"
  Execute transformation using writer "FileIo"
  Execute transformation using writer "FileIo"
  Execute transformation using writer "FileIo"
  Execute transformation using writer "FileIo"
  Execute transformation using writer "FileIo"
  Execute transformation using writer "twig"
  Execute transformation using writer "twig"
  Execute transformation using writer "twig"
  Execute transformation using writer "twig"
  Execute transformation using writer "twig"
  Execute transformation using writer "twig"
  Execute transformation using writer "twig"
  Execute transformation using writer "twig"
  Execute transformation using writer "twig"
  Execute transformation using writer "twig"
  Execute transformation using writer "twig"
  Execute transformation using writer "Graph"
   0.633s
Analyze results and write report to log .. 0.001s
```

## Credits

The plugin is based around [phpDocumentator](https://phpdoc.org/).

