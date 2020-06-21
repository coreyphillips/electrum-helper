INTRODUCTION
------------

electrum-helper is a series of helper methods for interacting with the electrum-client library. 


INSTALLATION
------------
 * With npm:
    * `npm install electrum-helper`
 * With yarn:
     * `yarn add electrum-helper`


USAGE
-----

    const { connectToPeer, getFeeEstimate, getNewBlockHeadersSubscribe } = require("electrum-helper");
    const coin = "bitcoin";
    connectToPeer({ coin }).then(async (peerResponse) => {
        const [blockHeader,feeEstimate] = await Promise.all([
            getNewBlockHeadersSubscribe({ coin }),
            getFeeEstimate({ coin })
        ]);
        console.log(peerResponse);
        console.log(blockHeader);
        console.log(feeEstimate);
    })

TODO
----
 * Add documentation containing more examples.
 * Remove old/deprecated methods.
