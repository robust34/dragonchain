# Dragonchain

The Dragonchain platform attempts to simplify integration of real business applications onto a blockchain. Providing features such as easy integration, protection of business data, fixed 5 second blocks, currency agnosticism, and interop features, Dragonchain shines a new and interesting light on blockchain technology.

#### No blockchain expertise required!

## Project Goals

1. Ease of integration of existing systems 
1. Ease of development for traditional engineers and coders unfamiliar with blockchain, 
distributed systems, and cryptography 
1. Client server style and simple RESTful integration points for business integration 
1. Simple architecture (flexible and usable for unforeseen applications) 
1. Provide protection of business data by default
1. Allow business focused control of processes
1. Fixed length period blocks 
1. Short/fast blocks 
1. Currency agnostic blockchain (multi­currency support) 
1. No base currency 
1. Interoperability with other blockchains public and private 
1. Adoption of standards as they become available (see ​W3C Blockchain Community 
Group blockchain standardization​) 


## Quick Links
* [Dragonchain Organization](https://dragonchain.github.io/)
* [Dragonchain Architecture Document](https://dragonchain.github.io/doc/DragonchainArchitecture.pdf)
* [Dragonchain Architecture Document DRAFT for comment](https://docs.google.com/document/d/1SRhBUeGN1dpm9sZsxTrqEHx0qL3_R3DPg-fcMUhUKWs)

## Support
[![Slack Status](https://dragon-chain-slack.herokuapp.com/badge.svg)](https://dragon-chain-slack.herokuapp.com)
Slack Team: [Dragonchain Slack Team](https://dragonchain.slack.com/)
Slack Support Channel: [#support](https://dragonchain.slack.com/messages/support/)
Email: support@dragonchain.org

## Maintainer
Joe Roets (j03)
joe@dragonchain.org

# Setup and Installation

### Python Dependencies

Dragonchain utilized Python 2.7

To install Python library dependencies, run the following:

    pip install -r requirements.txt

### Code Generation

Message classes and RMI services are generated by thrift templates.
If you have Apache Thrift installed you can regenerate these classes by using the gen_thrift setup command:

    python setup.py gen_thrift

### Keys

* Signing Key Generation `openssl ecparam -name secp224r1 -genkey -out <Dragonchain Home>/pki/sk.pem`
* Verifying Key Generation `openssl ec -in sk.pem -pubout -out <Dragonchain Home>/pki/pk.pem`

# Execution

## Transaction Service

    python <Dragonchain Home>/blockchain/transaction_svc.py --private-key <Dragonchain Home>/pki/sk.pem --public-key <Dragonchain Home>/pki/pk.pem
    
## Query Service

    python <Dragonchain Home>/blockchain/query_svc.py --private-key <Dragonchain Home>/pki/sk.pem --public-key <Dragonchain Home>/pki/pk.pem

## Blockchain Processor

    python <Dragonchain Home>/blockchain/processing.py --private-key <Dragonchain Home>/pki/sk.pem --public-key <Dragonchain Home>/pki/pk.pem

    --private-key (required - signing key for transaction service and processing module)
    --public-key  (required)
    --host        (defaults to localhost)
    --port, -p    (defaults to 8080)
    --phase       (required)

## Configuration

Configuration within yaml files within configs directory.

### Environment Variables

`BLOCKCHAIN_DB_HOSTNAME` = Hostname of the database instance (default localhost)

`BLOCKCHAIN_DB_PORT` = Port of the database server (default 5432)

`BLOCKCHAIN_DB_USERNAME` = Database username (default blocky)

`BLOCKCHAIN_DB_PASSWORD` = Database password (default None)

`BLOCKCHAIN_DB_NAME` = Blockchain database (default blockchain, also selects `.yaml` config and log file with same name)

# Contribution

Dragonchain uses a standard Feature Branch Workflow.

All feature development should take place in Git branch dedicated to that feature. A feature branch should be named starting with the ticket ID followed by a dash and a short description.

Issues are tracked within Github: [Dragonchain Issues](https://github.com/dragonchain/dragonchain/issues)

## Formatting

Code should follow the [PEP 8 Style Guide](https://www.python.org/dev/peps/pep-0008/) for Python code where possible. 

## Contributors

- Joe Roets - Principal Architect / Vision
- Eileen Quenin - Product Manager / Evangelist
- Brandon Kite - Lead Developer
- Dylan Yelton - Developer
- Michael Bachtel - DevOps / Developer
- Lucas Ontivero - Developer
- Adam Bronfin - Developer / Reviewer
- Benjamin Israelson - Developer / Reviewer
- Forrest Fisher - Program Manager
- Robbin Schill - Program Manager
- Krassi Krustev - Developer
- Rob Eickmann - iOS Developer
- Sean Ochoa - DevOps / Sysadmin
- Paul Sonier - Developer / Reviewer
- Steve Owens - Reviewer
- Mark LaPerriere - Reviewer
- Kevin Duane - Reviewer
- Chris Moore - Reviewer
- Brian J Wilson - Architect




# License

```
Copyright 2016 Disney Connected and Advanced Technologies

Licensed under the Apache License, Version 2.0 (the "Apache License")
with the following modification; you may not use this file except in
compliance with the Apache License and the following modification to it:
Section 6. Trademarks. is deleted and replaced with:

     6. Trademarks. This License does not grant permission to use the trade
        names, trademarks, service marks, or product names of the Licensor
        and its affiliates, except as required to comply with Section 4(c) of
        the License and to reproduce the content of the NOTICE file.

You may obtain a copy of the Apache License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the Apache License with the above modification is
distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
KIND, either express or implied. See the Apache License for the specific
language governing permissions and limitations under the Apache License.
```
