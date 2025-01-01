# Setup

Some general setup notes regarding your environment. This was used when publishing to npm. 

I found [this video](https://www.youtube.com/watch?v=J4b_T-qH3BY) to be a good watch to get you started. Note that this repository uses GitHub Workflow to publish to GitHub Packages on release but these steps can help you if looking for a crash course in even publishing to just npm.

### init and link 

When running test this was done on Mac OS

- Initialize with `npm init` to init the package
- You can use `npm init --scope=<yourscope>` if you want to create a scope for you package
- Create the `index.js` file that will contain your code
- Run `npm link` to link

### npm link error 

If you get errors trying to run npm link you may need to configure some things. I had to do the following

```command
mkdir "${HOME}/Packages/.npm-global"
npm config set prefix "${HOME}/Packages/.npm-global"
export PATH="${HOME}/Packages/.npm-global/bin:$PATH"
source ~/.zshrc
npm config get prefix
sudo chown -R $(whoami) $(npm config get prefix)/{lib/node_modules,bin,share}
```

> [!NOTE]
> On a Max using CTRL+SHIFT+. to see a hidden folder, since the name of folder in this example starts with a . it is hidden by default. You can toggle this in Finder using CTRL+SHIFT+.

### zshrc does not exist error 

If you get an error running `source ~/.zshrc` you may need to create this using the following steps

```command
touch ~/.zshrc
nano ~/.zshrc
export PATH="${HOME}/Packages/.npm-global/bin:$PATH"
```

Press `CTRL+X`, `Y` then `Enter`

Reload with `source ~/.zshrc`

## Testing

- Create a `script.js` file in the `test-folder`
- Add a `require` statement to require your module

> [!IMPORTANT]
> Use the package name used when running npm init

- Now you need to link to your package from the test folder
- `cd test-folder`
- `npm link <your package name>`
- At this point you will see a node_modules added to the test-folder
- Execute the script using `node script.js`

## Publishing

This is if publishing to npm, different if using the Workflow that is part of this repository

- cd to the `package` folder
- `npm login`
- Run `npm publish --access public` if public
- You can use scoped packages prefix with your scope  
