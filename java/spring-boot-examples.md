
# Spring Boot Examples

Turn map into collection

```
mapObj.value().stream().map(entry -> new DTOResponse(entry))
	.collect(Collectors.toList());

```

Retrieve value from id

```
this.mapObj.get(val);
```

or 
```
Optional<User> user = userMap.values().stream() .filter(u -> u.getId().equals(targetId)) .findFirst();
```

or if null

```
User foundUser = userMap.values().stream() .filter(u -> u.getId().equals(targetId)) .findFirst() .orElse(null);
```


Returning a responseEntity from java controller

```
ResponseEntity.status(httpStatus.OK).body(enty);
```