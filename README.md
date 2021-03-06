kRPCI
=====

kRPCI is a C++ client to kRPC for communicating with Kerbal Space Program (KSP). 

Using the Client Library
------------------------

* Copy the .cc, .cpp and .h files in src to your project directory
* Instantiate a KRPCI client object and use the generated functions in krpci_generated.cpp
* See krpci_test.cpp for a concrete example

Updating kRPCI
---------------

The kRPCI interface code is completely generated using Cheetah templates. kRPCI can be updated for each new version of KSP by simply regenerating the interface.

* The templates reside in  src/templates/*.tmpl
* Use krpci_generator.py to regenerate the client.
* To test, you can use krpci_test.cpp and the Makefile

Requirements:
------------

* Cheetah Templating Engine
* Kerbal Space Program
* kRPC and its dependencies

Cheetah Templating Engine
-------------------------

* kRPCI regeneration requires the Cheetah Templating Engine.
* Download from: https://pypi.python.org/pypi/Cheetah/2.4.4
* Extract this Cheetah-2.4.4.tar.gz
* cd Cheetah-2.4.4
* sudo python setup.py install

Other Assumptions
-----------------

* We expect KSP & kRPC server to be running
* We expect an active vessel in flight (in focus, in the game)
* The script fetches all the services & procedures using the KSP interface and generates the API we need.
* Then, krpci_test.cpp uses the generated KRPCI API (krpci_generated.cpp & krpci.hpp) to communicate with KSP



