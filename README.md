
# Username convention generator 🙎‍♂️

## Usage 

 1. To install it clone the repository: 
	 `git clone https://github.com/itasahobby/usernamesconventions.git`
 2. Create a json file with the following structure :
	 ```
	 {
		 "users":[
			{
				"name": "name1",
				"surname": "surname1",
			},
			{
				"name": "name2",
				"surname": "surname2",
			}
		]
	 }
	 ``` 
3. Program sintaxis:
	```
	usage: usernameconv.py [-h] [-j] [-s CONVENTIONS | -a CONVENTIONS] [-S SEPARATOR] -i INPUT_FILE -o OUTPUT_FILE

	Generates a wordlist of usernames according to different conventions for the given name and surname

	optional arguments:
	-h, --help            show this help message and exit
	-j, --output-json     The output is generated as a json file instead of a wordlist
	-s CONVENTIONS, --substitute-conventions CONVENTIONS	Specify a file with custom conventions and substitute them all
	-a CONVENTIONS, --add-conventions CONVENTIONS	Specify a file with custom conventions and add them to default ones
	-S SEPARATOR, --set-separator SEPARATOR	Specify a custom separator used for conventions
	-i INPUT_FILE, --input-file INPUT_FILE	Input json file
	-h, --help            show this help message and exit
	-j, --output-json     The output is generated as a json file instead of a wordlist
	-s CONVENTIONS, --substitute-conventions CONVENTIONS	Specify a file with custom conventions and substitute them all
	-a CONVENTIONS, --add-conventions CONVENTIONS	Specify a file with custom conventions and add them to default ones
	-S SEPARATOR, --set-separator SEPARATOR	Specify a custom separator used for conventions
	-i INPUT_FILE, --input-file INPUT_FILE	Input json file
	-o OUTPUT_FILE, --output-file OUTPUT_FILE	Output json file
	```
	> Notes: The default separator is &, if you are using your own convention rulset with a different one this parameter should be used to avoid errors or bad results.
	
## Advanced usage
You can add your own convention rulset or substitute the default one with the following syntax:
```
&name&surname_companyname
&name_&surname_companyname
```
The example above is assuming that the separator being used is the default one (&). 
Currently there are the following rules implemented:
* &name -> Name
* &1name -> First name (from 1 to 9, if it doesn't have it skips the rule)
* &surname -> Surname
* &1surname -> First surname (from 1 to 9, if it doesn't have it skips the rule)
* &n -> Name's first letter
* &s -> Surname first letter 