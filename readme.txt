All Steps:

npm install tailwindcss
npx tailwind init

This should create three new files in your project root: package.json, package-lock.json, and tailwind.config.js.

create a file in the src folder called input.css, and put the following code into it:
@tailwind base;
@tailwind components;
@tailwind utilities;

Go back to the project root, and replace the contents of tailwind.config.js with the following:
module.exports = {
  content: [
  "./build/**/*.{html,js}"
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}

After that, open your package.json file and replace its contents with the following:
{
  "scripts": {
    "build-css": "npx tailwindcss -i ./src/input.css -o ./build/static/output.css --watch"
  },
  "dependencies": {
    "tailwindcss": "^3.0.23"
  }
}

npm run build-css

npm install --save-dev live-server

live-server build