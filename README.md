# Shuttering applications

This should be used to enable a maintenance page for a product
The list of products is in [Jenkinsfile](Jenkinsfile) in the PRODUCT choices section.
Please add new ones as part of going live.
It is a drop down on jenkins to reduce the chance of mistakes.

You will need to build it once to refresh the list, so make sure you build it with shutter: off in aat

Note that shuttering is done via DNS
The DNS record has a 100s TTL

So it'll take approximately 2 minutes for shuttering to take affect


