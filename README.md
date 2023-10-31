# Strapi Starter Next 13, Tailwind, Typescript and Strapi

Strapi project based on template site which utilizes strapi backend, Next.js 13, tailwind css, and typescript to build a Saas product. Streamlines fast MVP development and allows for quick CMS copy and deployments

## Getting Started

1. Clone the repository locally:

```bash
  git clone https://github.com/acgriswold/strapi-nextjs-example.git
    or
  gh repo clone acgriswold/strapi-nextjs-example
```

2. Run `setup` command to setup frontend and backend dependencies:

```bash
  yarn setup
```

3. Next, navigate to your `/backend` directory and set up your `.env` file. You can use the `.env.example` file as reference:

```bash
HOST=localhost
PORT=1337
APP_KEYS="toBeModified1,toBeModified2"
API_TOKEN_SALT=tobemodified
ADMIN_JWT_SECRET=tobemodified
JWT_SECRET=tobemodified
TRANSFER_TOKEN_SALT=tobemodified
```

4. Start your project by running the following command:

```bash
  yarn build
  yarn develop
```

You will be prompted to create your first admin user.

![admin-user](https://user-images.githubusercontent.com/6153188/231865420-5f03a90f-b893-4057-9634-9632920a7d97.gif)

Great. You now have your project running. Let's add some data.

## Setting Up The Frontend

Next we need to switch to our `/frontend` directory and create our `.env` file and paste in the following. 

```bash
NEXT_PUBLIC_STRAPI_API_TOKEN=your-api-token
NEXT_PUBLIC_PAGE_LIMIT=6
NEXT_PUBLIC_STRAPI_FORM_SUBMISSION_TOKEN=your-form-submission-token
NEXT_PUBLIC_STRAPI_API_URL=http://localhost:1337

```

## Start Both Projects Concurrently

We can also start both projects with one command using the `concurrently` package.

You can find the setting inside the `package.json` file inside the root folder.

```json
{
  "scripts": {
    "frontend": "yarn dev --prefix ../frontend/",
    "backend": "yarn dev --prefix ../backend/",
    "clear": "cd frontend && rm -rf .next && rm -rf cache",
    "setup:frontend": "cd frontend && yarn",
    "setup:backend": "cd backend && yarn",
    "setup": "yarn install && yarn setup:frontend && yarn setup:backend",
    "dev": "yarn clear && concurrently \"cd frontend && yarn dev\" \"cd backend && yarn develop\""
  },
  "dependencies": {
    "concurrently": "^7.6.0"
  }
}
```

You can start both apps by running `yarn dev`.

## Conclusion

Hope you find this starter useful, it is a bare-bone example to help you get started quickly.

Would love to hear what you will build using it.

If you find bugs or have suggestions feel free to create issues.

Thank you and stay awesome.
