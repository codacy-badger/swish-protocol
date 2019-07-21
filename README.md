# adon-api-handshake [![Known Vulnerabilities](https://snyk.io/test/github/adonisv79/adon-api-handshake/badge.svg]
An API Authentication Mechanism in order to monitor and manage sessions between clients and an API.

## Project stats
* Package: [![npm](https://img.shields.io/npm/v/adon-api-handshake.svg)](https://www.npmjs.com/package/adon-api-handshake) [![npm](https://img.shields.io/npm/dm/adon-api-handshake.svg)](https://www.npmjs.com/package/adon-api-handshake)
* License: [![GitHub](https://img.shields.io/github/license/adonisv79/adon-api-handshake.svg)](https://github.com/adonisv79/adon-api-handshake/blob/master/LICENSE)
* CICD: [![Codacy Badge](https://api.codacy.com/project/badge/Grade/3709f3ab3b0c4380b5a41e010e8628c0)](https://www.codacy.com/app/adonisv79/adon-api-handshake?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=adonisv79/adon-api-handshake&amp;utm_campaign=Badge_Grade)
  * develop: [![Build Status](https://travis-ci.org/adonisv79/adon-api-handshake.svg?branch=develop)](https://travis-ci.org/adonisv79/adon-api-handshake) [![Coverage Status](https://coveralls.io/repos/github/adonisv79/adon-api-handshake/badge.svg?branch=develop)](https://coveralls.io/github/adonisv79/adon-api-handshake?branch=develop)
  * master: [![Build Status](https://travis-ci.org/adonisv79/adon-api-handshake.svg?branch=master)](https://travis-ci.org/adonisv79/adon-api-handshake) [![Coverage Status](https://coveralls.io/repos/github/adonisv79/adon-api-handshake/badge.svg)](https://coveralls.io/github/adonisv79/adon-api-handshake)

## How it works
The API Handshake is basically a Hybrid Encryption system (https://en.wikipedia.org/wiki/Hybrid_cryptosystem) which is built for managing short to medium term Client-Server sessions. This is usefull for ensuring that whenever a client needs to connect to an API, the transmitted communication medium is encrypted. On top of that, when that session is destroyed, the transmitted data are as good as gone! To continue communicating, the client needs to perform a new handshake. As of v1.1.0, we have added a double ratchet mechanism to even complicate things. :p

For more details on this project, please see the project wiki at https://github.com/adonisv79/adon-api-handshake/wiki

## Installation [![npm](https://img.shields.io/npm/v/adon-api-handshake.svg)]
The module is released and available in NPMJS (https://www.npmjs.com/package/adon-api-handshake) 
```
npm install adon-api-handshake --save
```

Full guide is in the Wiki

## History
### Migration to TypeScript (added in 1.2.2)
We have started unit testing and boy it is a mess as we need to validate through several possible ways anyone will mess your code thru invalid parameter injection. We need a standardized way to strict type it and no one comes close to TypeScript such that most projects are moving towards it.

*do not use 1.2.0, it pointed to the wrong index.js file and was hotfixed via 1.2.1 
*1.2.2 has a minor fix from 1.2.1 and works the same. only the file size changed as we removed the test tool codes

### Double Ratchet (added in 1.1.0)
We enhance the algorithm by applying a double ratchet approach similar to most messaging encryption apps. Each communication will basically generate a new private key and pass its new public key. these sets are used for the next request or response chain making it almost crazy to crack unlike in the previous version where getting the current session key allows a hacker to snoop thru ALL messages in the session. now they need to be part of the entire conversation chain or they will be lost.

[![Known Vulnerabilities](https://snyk.io/test/github/adonisv79/adon-api-handshake/badge.svg](https://snyk.io/test/github/adonisv79/adon-api-handshake)
