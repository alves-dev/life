# Events list

Aqui listarei todos os eventos possiveis

### Todos os eventos vao ter os seguintes campos:

```json
{
  "type": "EVENT_TYPE",
  "person_id": "f81ac9d2-f365-4254-a374-6vd2bb337e16",
  "datetime": "2024-01-23T14:45Z"
}
```
--------------------------------------------------------------


<a id="person_tracking"></a>
#### PERSON_TRACKING: *routing_key* -> _person_tracking_
```json
[
  {
    "type": "PERSON_TRACKING",
    "person_id": "f82ac9d8-f165-4254-a374-1ad2bb317e16",
    "datetime": "2024-01-23T14:45Z",
    "action": "CAME_IN",
    "local": "home",
    "origin": "Home assistant"
  },
  {
    "type": "PERSON_TRACKING",
    "person_id": "f82ac9d8-f165-4254-a374-1ad2bb317e16",
    "datetime": "2024-01-23T14:45Z",
    "action": "WENT_OUT",
    "local": "work",
    "origin": "Home assistant"
  },
  {
    "type": "PERSON_TRACKING",
    "person_id": "f82ac9d8-f165-4254-a374-1ad2bb317e16",
    "datetime": "2024-01-23T14:45Z",
    "action": "REMAINED",
    "local": "gym",
    "minutes": 45,
    "origin": "Home assistant"
  }
]
```
 - __action__: [CAME_IN, WENT_OUT, REMAINED]
--------------------------------------------------------------


<a id="exercise"></a>
#### EXERCISE: *routing_key* -> _exercises_
```json
{
  "type": "EXERCISE",
  "person_id": "f81ac9d8-f165-4254-a374-1ad2bb337e16",
  "datetime": "2024-01-23T14:45Z",
  "type_exercise": "RACE",
  "detail": {
    "origin": "Strava",
    "external_id": "2561523"
  }
}
```
--------------------------------------------------------------