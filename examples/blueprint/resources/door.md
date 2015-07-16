## Door [/doors/{door_id}]

A door represents a moveable object between two neighboring spaces.

:[Parameters](../api-blueprint/helpers/parameters.md param1:../data-structures/door/items/parameters/door_id.md)

### List Doors [GET /doors]

This action lists all doors.

:[Response](../api-blueprint/helpers/response.md code:"200"attribute:"List Doors")

### Get Door [GET]

This action returns one specific door.

:[Response](../api-blueprint/helpers/response.md code:"200" attribute:"Get Door")

### Secure Door [POST /doors/{door_id}/security]

This action locks/unlocks a door.

:[Parameters](../api-blueprint/helpers/parameters.md param1:../data-structures/door/items/parameters/door_id.md)


:[Success Request](../api-blueprint/helpers/request.md attribute:"Secure Door Request")

:[Success Response](../api-blueprint/helpers/response.md code:"201" attribute:"Get Door")


:[Error 404 Request](../api-blueprint/helpers/request.md attribute:"Secure Door Request 404" identifier:"Error 404")

:[Error 404 Response](../api-blueprint/helpers/response.md code:"404" attribute:"Secure Door Response 404")
