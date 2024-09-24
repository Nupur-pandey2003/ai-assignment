
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

import statistics

def compute_statistics(data):
    if not data:
        return "Data list is empty."

    mean = statistics.mean(data)
    median = statistics.median(data)
    try:
        mode = statistics.mode(data)
    except statistics.StatisticsError as e:
        mode = str(e)  # Handles the case where there is no unique mode
    variance = statistics.variance(data)
    std_dev = statistics.stdev(data)

    return {
        "Mean": mean,
        "Median": median,
        "Mode": mode,
        "Variance": variance,
        "Standard Deviation": std_dev
    }

if __name__ == "__main__":
    # Sample data
    data = [1, 2, 2, 3, 4, 5, 5, 5, 6]
    
    stats = compute_statistics(data)
    
    for key, value in stats.items():
        print(f"{key}: {value}")
