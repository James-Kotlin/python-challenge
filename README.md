# python-challenge
file handling and exception  handling

codes:

def read_and_modify_file():
    # Prompt the user for a filename
    filename = input("Enter the name of the file to read: ")
    try:
        # Try opening the file in read mode
        with open(filename, "r") as input_file:
            content = input_file.read()
        
        # Modify the content: reverse the text as an example
        modified_content = content[::-1]  # Reverses the text
        
        # Write the modified content to a new file
        output_filename = "modified_" + filename
        with open(output_filename, "w") as output_file:
            output_file.write(modified_content)
        
        print(f"Success! Modified content has been written to '{output_filename}'.")
    
    except FileNotFoundError:
        print(f"Error: The file '{filename}' does not exist.")
    
    except IOError:
        print(f"Error: Could not read the file '{filename}' due to an I/O issue.")
    
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

# Call the function to execute the challenge
read_and_modify_file()
