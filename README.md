# Chalk

Chalk is a shared classroom workspace for teachers and students. It brings a teacher's board, the class server, and a student phone app into one lesson, with voice and visual input options.

## What it includes

- A canvas for lesson notes, diagrams, quizzes, and classroom tools
- A local classroom server for room codes, roster updates, and board-to-phone sharing
- A Flutter app for students to join a room, read notes, and ask questions
- Optional local Gemma support through Ollama, with cloud AI adapters available when configured
- An optional Electron wrapper for desktop use

## Run locally

Requirements: Node.js 22 LTS. Flutter is needed only for the student app.

```sh
npm install
```

Copy `.env.example` to `.env` if you need to configure optional services. Keep real credentials in `.env`; do not commit them.

```sh
npm run dev
```

Open `http://localhost:3000` in a browser on the teacher computer. Phones must be able to reach that computer over the same local network.

## Checks and builds

```sh
npm run check
npx vitest run
npm run build
```

For the student app, run from `student/`:

```sh
flutter pub get
flutter analyze
flutter test
```

To package the desktop app on Windows, use `npm run build:electron:win`.

## Project layout

- `components/`, `hooks/`, and `store.ts` — teacher board interface and state
- `server/` and `server.ts` — classroom and AI services
- `student/` — Flutter student app
- `electron/` — desktop wrapper
- `api/` — serverless endpoints
- `tests/` — automated checks

See [the documentation index](docs/README.md), [contributing guide](CONTRIBUTING.md), and [security notes](SECURITY.md).

## License

Chalk is distributed under the MIT License. See [LICENSE](LICENSE).