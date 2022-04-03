# Standards and Practices for Pike & Pen

## Code of Conduct

1. Treat everyone with respect and love.
2. No cussing.
3. Keep all requests and issues professional and relevant to the work.
4. Have fun, be humble, and share your knowledge!

## Workflow

### General Gitflow

**Normal Flow** 
- maintain a `main` branch and a `dev` branch
- branch off of `dev` for new features
- make Pull Requests to `dev` from feature branches
- only merge *reviewed* code into `dev`
- when a **milestone** is complete, branch from `dev` to a new `release` branch
- the `release` branch will be QA'd
- if **stable**, merge `release` into `main` with a **release version number tag**. Also merge `main` into `dev` *after* the new release has been merged into `main`
- if `release` is deemed **unstable**, make a new `fix` branch off of `dev` for each issue that needs to be fixed. when all `fix` branches are complete, reviewed, and merged back into `dev`, merge into the `release` branch and re-submit for QA

**Hotfixes** 
- a hotfix is a term that we use to refer to *only* the fixes made to the `main` branch
- a hotfix will only be made for *severe* bugs found in `main`
- after a hotfix is finished, it should be incorporated into any active `dev` branch you are working on
- *only* lead devs or devs given special permission will make/complete hotfixes

### Branches

**Branch Naming** 
- `main` : the main branch
- `dev` : the working dev branch
- `feat-[issue #]-[name]` : a new feture branch ex: "feat-#3306-new-user-login"
- `fix-[issue #(if there is one)]-[description]` : a bugfix branch ex: "fix-order-form-submit" or "fix-#44566-order-form-submit"
- `release` : a release branch (do not forget the **version number tag!**)

### Commits

**Commit Format**

`type(scope):subject`

**Commit Guidelines**
- Each commit should contain files that all pertain to the same *scope*
- If you have changed multiple files that apply to different scopes, add and commit them separately
- Make your subject as direct and succinct as possible

**Commit Naming**

`type` : Select one of the following commit types. These are your *only* options for `type`

- **feat**: a new feature, module, component, or piece of functionality
- **fix**: a bugfix to your code, dealing with github issues, etc.
- **docs**: changes to the README, changing, making, or removing comments in the code
- **art**: changes to any art asset, adding an image, etc.
- **refactor**: refactoring code for optimization or changing the code to meet new package demands, changing a `let`  to a `const`, etc.
- **test**: all things related to unit testing. creating, refactoring, removing tests. *NO* changes to production code
- **update**: updating gulp, webpack, or package.json files. This *does not* include refactoring production code to work with the new updates.
- **workaround**: a temporary fix until a more robust solution is found
- **setup**: the creation of a new file, this can also include writing the boilerplate code for a new file (NOTE: this is the *only* `type` where a `subject` is not neccessary)

`scope`: the single file, folder, or module that is being affected. Only use one or two word descriptions.

`subject`: Favor imperative mood, present tense, active voice, and start with verbs. Don't use a period at the end. Think of it as a newspaper headline.

`body`: (optional): If necessary, provide additional context that can help other developers in the future.

**Commit Examples**

`art(/sprites): added sprites for enemy-1`

`feat(user.class.js): added firstName property`

`fix(form.css): changed x-axis padding`

`setup(like-button.js)`


## Formatting

### General

- indents = 4 spaces
- there are 3 sizes of comments

```
// [///// SECTION NAME /////]

// ----- sub-section name -----

// explination about a function, line of code, or whatever else

/**
*   multiline explination about a function, line of
*   code, or whatever else
*/
```

### Filenames

**Gamemaker Files**

All files will contain a prefix limited to 3 letters or less followed by an "_" and then the name of the file. Each script should only contain *one* thing (function, class, database format, etc.)

- `scr_[scriptName]`: a script containing a function, script name always follows camel casing. function name should always match script name. ex: `scr_myScript`
- `cls_[ClassName]`: a script containing a class. Class name is camel case with a capital first letter. ex: `cls_MyClass`
- `db_[DatabaseName]`: contains a database structure or database. Camel case with capital first letter. ex: `db_MyDatabase`
- `obj_[objectName]`: an object asset. camel case naming. ex: `obj_player`
- `spr_[spriteName]`: sprite asset. Camel casing. ex: `spr_playerSprite`