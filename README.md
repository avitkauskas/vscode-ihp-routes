# IHP Routes Syntax Highlighting

A VS Code extension that provides syntax highlighting for the IHP web framework's `[routes| ... |]` quasi quotes in Haskell files.

## Features

Highlights the following elements:

- **HTTP methods**: `GET`, `POST`, `PUT`, `PATCH`, `DELETE`, `WS`, `HEAD`
- **URL paths**: Static path segments
- **Path captures**: `{param}` and `{+splat}` syntax
- **Query parameters**: `?param&param` syntax
- **Field aliases**: `#alias` syntax
- **Action names**: `*Action` functions
- **Comments**: `-- comment` lines

## Example

```haskell
[routes|webRoutes
GET    /Posts              PostsAction
GET    /NewPost            NewPostAction
POST   /CreatePost         CreatePostAction
GET    /ShowPost?postId    ShowPostAction
GET    /EditPost?postId    EditPostAction { postId = #id }
|]
```

## Installation

From the VS Code Marketplace:

1. Open VS Code Extensions (`Ctrl+Shift+X`)
2. Search for "IHP Routes"
3. Install and reload

From a `.vsix` file:

```bash
code --install-extension ihp-routes-quasi-0.1.0.vsix
```

## Development

```bash
npm install
npm run compile
F5 to test
```

## Publishing

```bash
vsce package
vsce publish -p <publisher-token>
```

## License

MIT