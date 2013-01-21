# OAuth Request XQuery Library

An XQuery library module for signing and making OAuth requests (e.g., needed to use the Twitter API),
forked from the version [originally written by Norm Walsh](http://norman.walsh.name/2010/09/25/oauth).

## Changes from Norm Walsh's original

This version sheds the reliance on the external hashing service for HMAC-SHA1 signing algorithm 
and on Mark Logic's HTTP functions for making HTTP requests, in favor of the cross-platform [EXPath HTTP Client](http://expath.org/spec/http-client) and [EXPath Crypto](http://expath.org/spec/crypto) modules.

Since we lack a cross platform method of generating a good random string to help generate
the OAuth nonce, I have substituted the original Mark Logic extension function for one from 
the XQuery implementation I use, namely, eXist-db.  Most XQuery processors have their own 
equivalents to these functions, making adapting this to other processors easy, but I hope 
that the EXPath community creates a standard mechanism for these functions.  When they do,
I'll be able to remove the eXist-db dependency.

I have repackaged the library in the [EXPath Package format](http://www.expath.org/spec/pkg) for 
convenient installation in XQuery implementation that support it.  That said, nothing's preventing you
from grabbing the library module out of the content directory

This package has been tested with eXist 2.0RC2.  

## Installation for eXist-db

To install in eXist-db, clone this repository and run [Apache Ant](http://ant.apache.org/), which will construct an 
EXPath Archive (.xar) file in the project's build folder. Then install the package via the eXist-db Package Manager, 
or place it in eXist-db's 'autodeploy' folder.

## Usage

### Import the module

    import module namespace oa="http://marklogic.com/ns/oauth";

(To be completed...)