# Python code to convert Wiki markup text to HTML code

`using the re.sub function from the re module to perform a regular expression-based substitution.

It searches for the pattern \[(.*?)\]\((.*?)\) in the input content, where (.*?) captures the text inside the square brackets and the parentheses.

Then, it replaces the match with <a href="\2">\1</a>, where:

\1 represents the first captured group (the text) and \2 represents the second captured group (the link).`

import re

def rewrite_text_file(input_file, output_file):
    with open(input_file, 'r') as file:
        content = file.read()   
        
  
 `Replace [text](link) with <a href="link">text</a>`
 
   modified_content = re.sub(r'\[(.*?)\]\((.*?)\)', r'<a href="\2">\1</a>', content)
    with open(output_file, 'w') as file:
        file.write(modified_content)
    print("File rewritten successfully!")

`Usage example`

input_file_path = 'input.txt'   Provide the path to your input file here
output_file_path = 'output.txt' Provide the path to the desired output file here
rewrite_text_file(input_file_path, output_file_path)
