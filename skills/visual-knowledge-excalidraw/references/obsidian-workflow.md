# Obsidian Validation Loop

This skill is not finished when the file exists. The default standard is:

generate -> export -> inspect -> revise

## Runtime assumptions

Before attempting validation, confirm:

- current working directory
  - the skill assumes it is already running inside the target Obsidian vault or one of its subfolders
- `target_file_name`
  - the filename to generate in the current directory
  - recommended pattern: `[topic].[diagram-type].excalidraw.md`
- `target_file_path`
  - usually `./<target_file_name>`
  - it must resolve to a path inside the target vault
- `active_note_target`
  - a reliable way to make the generated note the active file in Obsidian before export
- `export_command`
  - a non-interactive or reliably repeatable command / command id that exports the current Excalidraw file to PNG
- `png_file_path`
  - the expected exported PNG path
- `screenshot_target`
  - preferably the exported PNG, otherwise the live Excalidraw view in Obsidian

If any critical value is missing, do not pretend the loop can run. Say clearly that only a draft can be produced.

## Default loop

### 1. Generate the file content

Build the full `.excalidraw.md` using `json-schema.md` and `element-templates.md`.

Requirements:

- clear filename
- valid JSON
- frontmatter includes `excalidraw-autoexport: png`

### 2. Confirm the output path is inside the target vault

Before writing the file, make sure `target_file_path` is inside the target Obsidian vault.

Being in a subfolder of the vault is valid.

If `target_file_path` is outside the target vault, stop the validation loop here and report that PNG validation is blocked until a vault-relative target path is provided.

### 3. Write to the current directory

Write the file to:

`<target_file_path>`

Record:

- the generated note path
- the expected PNG path

### 4. Make sure Obsidian is targeting this note

Before export, make sure the generated note is the active Obsidian file.

If you cannot reliably open or focus the generated note in Obsidian, stop here and report that PNG validation is blocked because export would operate on an unknown active file.

### 5. Trigger export

Run `obsidian command` with `export_command`.

The export command should:

- avoid manual dialog interaction
- export the currently active Excalidraw file
- write a predictable PNG file

If `export_command` depends on the active Obsidian file, make sure the generated note is the file Obsidian is actually operating on. If not, say that export validation is blocked.

If the only available command opens an export dialog instead of actually exporting, do not count that as a successful export.

### 6. Read or capture the PNG

Preferred order:

1. read the exported PNG directly
2. use `obsidian screenshot` on the exported result or the active Excalidraw view

Only after an image is available does real validation begin.

### 7. Review the image

Review it against the original design goals and `optimization-checklist.md`:

- is the main flow immediately visible?
- do the connections land on the right elements?
- are branching, convergence, and loops expressed by the right structures?
- is the text readable?
- do evidence blocks help rather than dominate?

### 8. Revise in place

If problems are found:

- change only the nodes, arrows, regions, or text sizing that need change
- do not rebuild the whole diagram unless the structure is fundamentally wrong
- write the update back to the same path
- export PNG again

### 9. Stop condition

Stop when:

- the main reading path is clear
- there is no obvious clipping, misbinding, or overlap
- the structural pattern matches the meaning
- the text is readable at the exported size
- no major quality issue remains that would need a caveat

Default maximum: 3 rounds. If issues remain after that, report the remaining problems rather than looping forever.

## Failure handling

### Write failure

- report a current-directory or path problem
- return the generated content or draft location if possible

### Export failure

- report failure in the `obsidian command` step
- make it clear that generation succeeded but export automation did not
- keep the `.excalidraw.md` draft path for manual review

### Screenshot failure

- report failure in the visual validation step
- do not claim the PNG review completed
- return the draft and mark validation as incomplete

## Final response checklist

Report:

- `.excalidraw.md` path
- PNG path
- diagram type chosen
- how many export / review rounds ran
- what the final revision improved
