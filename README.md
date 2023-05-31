# Convert-markup-Text-to-HTML
Python code to convert Wiki markup text to HTML code

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
