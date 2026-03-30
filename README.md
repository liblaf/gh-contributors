# gh-contributors

Automatically generate an svg with all contributors for your repository.

## Usage

```
https://contrib.nn.ci/api?repo=[user/repo]
```

Or generate online with [gh-contributors](https://contrib.nn.ci/)

The following parameters are available:

- repo: The repository to generate the svg for, e.g. `xhofe/gh-contributors`, required & multiple;
- cols: Number of avatars per row (default: 12)
- pages: Number of pages to generate per repo (default: 1), 100 contributors per page
- radius: The radius of the avatars (default: 32)
- space: The spacing between avatars (default: 5)
- no_bot: Do not show bots (default: false)
- min_contributions: Only show contributors with at least this number of contributions (default: 0)
- compress: The height/width of each avatar after compression (default: radius \* 4, 0 to disable)

## Example

![Contributors](https://contrib.nn.ci/api?repo=alist-org/alist&repo=alist-org/alist-web&repo=alist-org/docs)

## Getting Started

Use Node.js 20 and `pnpm` for the smoothest local and Vercel setup.

Install dependencies:

```bash
pnpm install
```

Optionally add a GitHub personal access token to raise the GitHub API rate limit:

```bash
cp .env.example .env.local
```

Then set `PAT=your_github_token` in `.env.local`.

Run the development server:

```bash
pnpm dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

## Deploy To Vercel

This project can be deployed to Vercel as a standard Next.js app.

1. Import the repository into Vercel.
2. Keep the detected framework as `Next.js`.
3. Use the default root directory.
4. Set the environment variable `PAT` in the Vercel project settings if you want higher GitHub API limits.
5. Set the Node.js version to `20.x` in Vercel project settings.
6. Deploy.

Vercel will detect `pnpm-lock.yaml` automatically. If you need to fill the commands manually, use:

```bash
Install Command: pnpm install
Build Command: pnpm build
```

No special output directory is required.

Notes:

- The app uses an on-disk cache locally.
- On Vercel, the cache is automatically stored in `/tmp`, which is writable but ephemeral between executions.
