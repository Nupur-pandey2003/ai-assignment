
def load_and_display_csv(file_path):
    try:
        df = pd.read_csv(file_path)

        print("CSV file loaded successfully!")
        print(df)
    except FileNotFoundError:
        print(f"Error: The file '{file_path}' was not found.")
    except pd.errors.EmptyDataError:
        print("Error: The file is empty.")
    except pd.errors.ParserError:
        print("Error: There was a problem parsing the file.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

load_and_display_csv('your_file.csv')
ent

