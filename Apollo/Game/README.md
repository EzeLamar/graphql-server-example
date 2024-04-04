# Games Apollo examples
Some examples of how to write the query functions in the Frontend side.

## Get Game by Id
```GraphQL
query GameQuery($id: ID!) {
  game(id: $id) {
    title,
    reviews {
      id,
      rating
    }
  }
}
```

### Variables
```GraphQL
{
  "id": "1",
}
```
## Get all Games
```GraphQL
query GamesQuery {
  games {
    id,
    title,
    platform
  }
}
```

## Add Game
```GraphQL
mutation AddMutation($game: AddGameInput!) {
  addGame(game: $game) {
    id,
    title,
    platform
  }
}
```

### Variables
```GraphQL
{
  "game": {
    "title": "a new game",
    "platform": ["switch", "ps5"]
  }
}
```

## Delete Game
```GraphQL
mutation DeleteMutation($id: ID!) {
  deleteGame(id: $id) {
    id,
    title,
    platform
  }
}
```

### Variables
```GraphQL
{
  "id": "3"
}
```

## Edit Game
```GraphQL
mutation EditMutation($id: ID!, $edits: EditGameInput!) {
  editGame(id: $id, edits: $edits) {
    id,
    title,
    platform
  }
}
```

### Variables
```GraphQL
{
  "id": "2",
  "edits": {
    "title": "a new game",
  }
}
```