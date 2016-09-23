# cmacctest

Sample files for Cmacc

Files are working with the electron editor that can be downloaded from common-accord repo.

The editor allows the creation of documents in a way similar to CommonAccord solution, but syntax is slightly changed from generic CommonAccord, to allow better/easier editing of content, including debugging for docs. The language is more structured and it introduces some limitations (at least in the current version):

* Pros: editor can be installed easily (dmg for Mac), and it “compiles” the text as it is entered, so you can easily spot unknown keys, or links to unknown files. And you do not have to enter HTML, the text can have carriage returns, indentation etc natively
 
* Cons: you cannot assign a key to a key, which forces carrying over the keys from one file to another if you want to set them later in the process.
 
You can download this new editor download here: https://github.com/wilmveel/cmacc-electron/releases/ 

This is still early stage but it is worth exploring and feel free to provide feedback as you play with it.

Some tips because it is still a first release and not everything is perfect:

- to load files, open a directory (cmd O or menu) then select the file from the list of files in the left column

- files cannot be saved unless they compile, so you may have to use an external editor to quickstart a project

- if you use an external editor, you should close the editor window and re-load the directory to get the latest version of the file uploaded

- you can use the “Dev” option in the top menu to see what is happening with the file, which is useful for debugging docs


How it works:

1. To set parameters:

$ key = value

2. To call a file and set key within the file called

$ key = [link to file] => {
 "key" : value
}

3. The value within a linked file can be a value or another file.
For example see the HelloWorld.cmacc file in this repo:

$ person = [../ID/_person.cmacc] => {
}

$ name_Full = [../ID/_person_full.cmacc] => {
	"person" : person
}

{{person.gender.His_Her}} name is {{name_Full}} and {{person.gender.he_she}} lives in {{person.city}}
