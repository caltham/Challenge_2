# **Challenge_2**

**The goal of this project is to apply software-engineering best practices to the loan qualifier application so as to include new features and enhancements; allowing users the ability to save their qualifying loans to a CSV file.**

## Technologies

<img width="523" alt="C2_Imports" src="https://user-images.githubusercontent.com/94569323/145520923-16bc8ecb-9e52-41b8-b9fc-160d0eb9060c.png">

After importing these required technologies and following the steps below, the program should be capable of functioning properly.

## Installation Guide

**Add a function named 'save_csv' that uses the csv library to save the qualifying data as a file:**

~~~
def save_csv(csvpath, qualifying_loans):
    csvpath = Path(csvpath)
    header = ["Lender", "Max Loan Amount", "Max LTV", "Max DTI", "Min Credit Score", "Interest Rate"]
    with open(csvpath, "w", newline = "") as csvfile:
        csvwriter = csv.writer(csvfile)
        csvwriter.writerow(header)
        for item in qualifying_loans:
            csvwriter.writerow(item)
~~~

**Create a new function named 'save_qualifying_loans' that uses '.confirm.ask' to ask the user if they want to save their qualifying loans, and uses 'questionary' to ask for the output file path:**

~~~
def save_qualifying_loans(qualifying_loans):
    csvpath = questionary.confirm("Do you want to save the file?").ask()
    csvpath = questionary.text("Enter an output file path (.csv):").ask()
~~~

**Integrate the 'save_csv' function into the 'save_qualifying_loans' function:**

~~~
def save_qualifying_loans(qualifying_loans):
    csvpath = questionary.confirm("Do you want to save the file?").ask()
    csvpath = questionary.text("Enter an output file path (.csv):").ask()
    csvpath = Path(csvpath)

    return save_csv(csvpath, qualifying_loans)
~~~

## Usage

**After all of the required technologies and functions have been installed and integrated into the application, the program should be capable of functioning properly.**
Let's give it a try!

<img width="741" alt="C2_Term" src="https://user-images.githubusercontent.com/94569323/145528487-c7245ede-9a97-4272-9e5b-62a383ad865f.png">

**Click the 'Run' button to start the program. As shown in the image above, the user should be prompted to enter a file path to a rate-sheet.**
Proceed by entering the path of the file named 'daily_rate_sheet.csv' which is located in the data folder.

<img width="737" alt="C2_Term2" src="https://user-images.githubusercontent.com/94569323/145530401-70d29c1b-f582-4861-bd43-10f7fe221a3a.png">

**Fill out the prompts by providing a credit score, current amount of monthly debt, total amount of monthly income, desired loan amount, and a home value. As shown above, the user will then be provided with their DTI, LTV, as well as the number of loans for which they qualify.**
The user will be asked is they wish to save the file.

<img width="996" alt="C2_Term3" src="https://user-images.githubusercontent.com/94569323/145531928-b2719672-2d87-4491-a9a4-6a382bd98bc8.png">

**As shown above, if the user wishes to save their file they are prompted to input a csv file path that will serve as the location of the new file.**
In the upper right hand corner of the photo above you can see that the 'output_sample_file_2' has been saved into the data folder.

## Contributors

Chancie Altham:
Developer

## License

MIT License has been added to the project.