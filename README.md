# entitlement-patterns

This demonstrates three patterns while working in DAML. 

## Building and Viewing

Best is to simply open the project in VS code, and look at the scenario in `daml/Desk.daml`. 

Alternatively, the Navigator can be used to inspect all the objects. It can be started with `daml start`.

## Delegation of Authority 

The first pattern is delegation of Authority, of how a desk delegates responsibility and rights to one or more members and admins. The `Desk` contract really just undersigns the ability of its members to act on its behalf, undersigning all the consequences that have been laid out. In this case, even though the desk does not sign off on `Wires` directly (though it *may* do so), the resulting `Wire`s nevertheless put the desk into an obligable position.

## Parties are not always people

The desk in this model is not a person. Nevertheless, if has the capacity to undersign contracts and to act. Practically, the desk in this case is a series of bots or triggers which acts programmatically to disclose contracts, and to onboard admins at inceptions.

## The Public party 

The public party is a ledger participant which does not exercise any choices, but is sometimes indicates as an `observer` on contracts that the stakeholders want to make completely public. Practically, the public party is a real party whose security tokens are made entirely public. That way, any user (with access to the ledger) may use that token to query the ledger for public contracts.

## Not shown: Multi-entity nondisclosure 

The module, as written, does not work if the desk members need to be hidden completely from the Treasurer. The funding is explicitly disclosed to the desk members, and therefore, the (some) of the desk members are disclosed to the treasurer. This is possible to do, however. 