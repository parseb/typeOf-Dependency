# typeOf-Dependency


## an idea
____________
Dependencies:
- can be managed
- can manage trusting dependents, or
- can be wrapped in yet another dependency (most popular choice)

<br>

There is no self-evident value in stubornly kepping a protocol at an address, particularly when the only imaginative way of doing so departs from the nature or sacrificies a core value of the underlying substrate. This follows brand-addressability, web2 packet management and platform building logic which retroactively justifies equating a contract address to the illusory notion of a permalink.  <br>

Potential Alternatives:

- Immutable Registry Mapping: 
```
/// @notice This and 0 are the only future relevant fixed points in the universe
contract ImmutableRegistry {
  event movedOffice(address indexed _oldAddress, address _newAddress);
  mapping(address=>address) public OldtoNew;
  
  function newOfficeAddress(address new_) { 
    OldtoNew[msg.sender] = new_;
    emit movedOffice(msg.sender, new_);
  }
}
```
So, instead of sacrificing immutability and logical-content-addressability (I am funny, thanks for noticing), one signals to the world in a standard way a change in location / new version of the immutable protocol. Better composability would have it so that on such an event, all the dependents are pointed to a new address. This can be done in the dependant, which brings us the the next pattern; or on calling newOfficeAddress() if the dependents registered themselves as dependants and provided sufficient gas for their state (address pointing to protocol) to be changed. The later is slightly less problematic than the most popular patterns.

_____
### modifier isUpgradeable(*args)

if (mapping[msg.sig] != address(this)) ISelf(mapping[msg.sig]).call(msg.sig, args) 


____

### Contract type composable interface



______
### Upgrade me please! (what did I mean by this?)



_____________

### Why is this any better?

"Trustless" depends on immutability which is a proprety that I here define as the imminent delivery on the expectation that the logic that I see and know and sign on is what will be executed. Largely, upgradeable proxies break this pattern as what you're calling upon is a window advertisement. By the time you get in and reach the counter, the terms of the advertisement have changed.






