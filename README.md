> Demo: a SvelteKit project that reads from a local SQLite database

Original code from `https://github.com/kisaragi-hiu/demo-sveltekit-sqlite`

Read the full doc [https://kisaragi-hiu.com/kemdict-sveltekit-sqlite/](https://kisaragi-hiu.com/kemdict-sveltekit-sqlite/)

## what I do and learn after clone the original repo

- update every version of the `package.json` file, then run `npm update`, `npm upgrade`.
- change from *Adapter Netlify* to *Adapter Auto* in `package.json` and the setup in `svelte.config.js`.
- update the `src/routes/+pages.svelte` file so it can run on my local machine.
- download the database and put it at the root. you can find the database url in Makefile file.

## how to setup

Clone this repo.

Then cd into the dir 

Then run:

```
npm install

npm run dev
```

## todo

- Integrate CRUD function
