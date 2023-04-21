---
title: Run a Typescript file with Node.Js
layout: default
---
# Run a Typescript file with Node.Js


To run the TypeScript file from a Windows command line, you need to have Node.js installed on your machine. Here are the steps to run the file:

1. Open a command prompt by pressing the `Windows key` + `R` on your keyboard, typing `cmd`, and then pressing `Enter`.

2. Navigate to the directory where your TypeScript file is located using the `cd` command. For example, if your file is located in `C:\Users\YourUsername\Documents\my-project`, you can navigate to that directory by typing the following command:

   ```
   cd C:\Users\YourUsername\Documents\my-project
   ```

3. Use the following command to install the necessary dependencies (if you haven't already):

   ```
   npm install typescript @types/node
   ```

4. Compile your TypeScript file using the following command:

   ```
   npx tsc your-file-name.ts
   ```

   This will create a JavaScript file in the same directory as your TypeScript file.

5. Run the JavaScript file using the following command:

   ```
   node your-file-name.js
   ```

   This will execute your TypeScript code and output the result in the console.

Note that you should replace `your-file-name` with the actual name of your TypeScript file (without the `.ts` extension) in the commands above.
