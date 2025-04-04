---
layout: default.md
title: "User Guide"
pageNav: 3
---

# VitaBook User Guide

**VitaBook** is a **desktop application for freelance nutritionists based in Singapore** to manage patient profiles, dietary information, and follow-ups efficiently. Built for speed and efficiency, VitaBook integrates a powerful **Command Line Interface (CLI)** with a clean **Graphical User Interface (GUI)**, allowing you to quickly retrieve and update patient records while on the go.

### Table of Contents

#### [1. Introduction](#1-introduction)
- [1.1 Key Features](#11-key-features)
- [1.2 Quick Start](#12-quick-start)
- [1.3 Instructions about Commands](#13-instructions-about-commands)

#### [2. Features](#2-features)

##### [2.1 To Navigate Patient Care](#21-to-navigate-patient-care)
- [2.1.1 Adding a Patient](#211-adding-a-patient-add)
- [2.1.2 Listing all Patients](#212-listing-all-patients-list)
- [2.1.3 Editing a Patient](#213-editing-a-patient-edit)
- [2.1.4 Changing a Patient's Priority](#214-changing-a-patients-priority-priority)
- [2.1.5 Adding a Remark to a Patient](#215-adding-a-remark-to-a-patient-remark)
- [2.1.6 Locating Patients by Name](#216-locating-patients-by-name-find)
- [2.1.7 Filtering Patients](#217-filtering-patients-filter)
- [2.1.8 Sorting Patients](#218-sorting-patients-sort)
- [2.1.9 Deleting a Patient](#219-deleting-a-patient-delete)
- [2.1.10 Clearing all Patient Entries](#2110-clearing-all-patient-entries-clear)

##### [2.2 To Provide a Convenient and Pleasant Experience](#22-to-provide-a-convenient-and-pleasant-experience)
- [2.2.1 Viewing Help](#221-viewing-help-help)
- [2.2.2 Undoing the Last Change](#222-undoing-the-last-change-undo)
- [2.2.3 Redoing the Last Undo](#223-redoing-the-last-undo-redo)
- [2.2.4 Navigating Through Command History](#224-navigating-through-command-history--and-)
- [2.2.5 Toggling between Light Mode and Dark Mode](#225-toggling-between-light-mode-and-dark-mode)
- [2.2.6 Exiting the Program](#226-exiting-the-program-exit)
- [2.2.7 Saving the Data](#227-saving-the-data)

##### [2.3 Bonus for Advanced Nutritionists](#23-bonus-for-advanced-nutritionists)
- [2.3.1 Edit the Data File Directly](#231-editing-the-data-file-directly)

##### [3. FAQ](#3-faq)

##### [4. Known Issues](#4-known-issues)

##### [5. Command Summary](#5-command-summary)

##### [6. Glossary](#6-glossary)

##### [7. Java Setup Instructions](#7-java-setup-instructions)

--------------------------------------------------------------------------------------------------------------------

## 1. Introduction

### 1.1 Key Features

VitaBook is built just for you, nutritionists — with commands tailored to your daily workflow. From adding and editing patient records to sorting, filtering, and setting priorities, everything is designed to help you stay organised, focused, and in control of your care delivery.

- **[Add Patient](#211-adding-a-patient-add)** — `add` : Add a new patient with complete details.
- **[Edit Patient](#213-editing-a-patient-edit)** — `edit` : Modify an existing patient’s information.
- **[Priority](#214-changing-a-patients-priority-priority)** — `priority` : Change a patient's priority by their index.
- **[Filter](#217-filtering-patients-filter)** — `filter` : View patients by priority, diet, gender, or meeting date.
- **[Sort](#218-sorting-patients-sort)** — `sort` : Sort patients by priority, name, or diet.

[↓ Go to Command Summary](#command-summary)

### 1.2 Quick start

1. Ensure you have Java `17` or above installed in your computer.<br>
   **Mac users:** Ensure you have the precise JDK version prescribed [here](https://se-education.org/guides/tutorials/javaInstallationMac.html).<br>
   **Check/Install Java:** See [Java Setup Instructions](#java-setup-instructions) at the bottom of this guide.

2. Download the latest `.jar` file [here](https://github.com/AY2425S2-CS2103T-F11-2/tp/releases)!

3. Copy the file to the folder you want to use as the _home folder_ for your own VitaBook.

4. Open a command terminal and use the `cd` command to navigate to the folder containing the `.jar` file.

5. Type the command `java -jar vitabook.jar` to run the application. A GUI similar to the one below should appear in a few seconds. Note that the app contains some sample data.<br>

<a href="images/Ui.png">

<img src="images/Ui.png" alt="Ui" style="width: 100%; max-width: 700px; display: block;"/>
</a>

*Figure 1: The VitaBook UI, showing layout and sample data*<br>

6. Try typing the command in the command box and press *Enter* to execute it.<br>
   e.g. typing `help` and pressing *Enter* will open the help window. Let's try some out!:

<p style="padding-left: 20px">

* `list` : Lists all patients.

* `add n/John Doe g/m h/1.78 w/70 no/98765432 e/johnd@example.com a/John Street, block 123, #01-01 d/low sodium m/2025-01-25 pr/LOW` : Adds a new patient named `John Doe` to your VitaBook.

* `delete 3` : Deletes the 3rd patient in the current list.

* `clear` : Deletes all patients.

* `exit` : Exits the app.
</p>

7. Feel free to explore further the functionalities of VitaBook by following [Features](#features)!

### 1.3 Instructions about Commands

These are a few things to take note while exploring VitaBook!

1. Command keywords are case-sensitive.<br>
   e.g. `delete 1` is a known command, while `Delete 1` is an unknown command.

2. Words in `UPPER_CASE` are the parameters to be supplied by the user.<br>
   e.g. in `add n/NAME`, `NAME` is a parameter which can be used as `add n/John Doe`.

3. Items in square brackets are optional.<br>
   e.g `n/NAME [al/ALLERGY]` can be used as `n/John Doe al/fish` or as `n/John Doe`.

4. Items with `…`​ after them can be used multiple times including zero times.<br>
   e.g. `[al/ALLERGY]…​` can be used as ` ` (i.e. 0 times), `al/milk`, `al/milk al/peanut` etc.

5. Parameters for `add` and `edit` commands can be in any order.<br>
   e.g. if the command specifies `n/NAME no/PHONE`, `no/PHONE n/NAME` is also acceptable.

6. Extraneous parameters for commands that do not take in parameters (i.e. `help`, `list`, `exit`, `undo`, `redo` and `clear`) will be ignored.<br>
   e.g. if the command specifies `help 123`, it will be interpreted as `help`.

7. If you are using a PDF version of this document, be careful when copying and pasting commands that span multiple lines as space characters surrounding line-breaks may be omitted when copied over to the application.

--------------------------------------------------------------------------------------------------------------------

## 2. Features

### 2.1 To Help You Navigate Patient Care

#### 2.1.1 Adding a Patient: `add`

Adds a new patient to your VitaBook with their complete details.

Format: `add n/NAME g/GENDER h/HEIGHT w/WEIGHT no/PHONE e/EMAIL a/ADDRESS d/DIET pr/PRIORITY m/MEETING_DATE [al/ALLERGY]…​`

<box type="tip" seamless>

**Tips/Constraints:**
1. A patient can have any number of allergies (including 0).

2. Emails must be unique i.e. duplicate emails are not allowed.

3. Patient names can be duplicated i.e. duplicate names are allowed.

4. Gender must be `m` or `f` (case-insensitive).

5. Height must be between `0.50` and `3.00`.

6. Weight must be a positive integer.

7. Priority must be one of the following: `high`, `medium`, `low` (case-insensitive).

8. Diet must be one of the following: `regular`, `low sodium`, `low fat`, `low carb`, `low sugar` (case-insensitive).

9. Meeting date must be in the format `YYYY-MM-DD`.

10. Phone number must be a positive integer of **exactly** 8 digits and starts with 6, 8 or 9.
</box>

Examples:
* `add n/John Doe g/m h/1.78 w/70 no/98765432 e/johnd@example.com a/John Street block 123, #01-01 d/low sodium pr/LOW m/2025-01-25`
* `add n/Betsy Crowe e/betsycrowe@example.com g/f a/Newgate Prison h/1.68 w/50 no/97867564 d/low fat pr/MEDIUM m/2025-02-24 al/peanuts al/milk`

<br>

#### 2.1.2 Listing all Patients: `list`

Shows a list of all the patients in your VitaBook.
If you have previously used `filter` or `find` to narrow down the patient list, use the `list` command to reset the display and show all patients again.

Format: `list`

<br>

#### 2.1.3 Editing a Patient: `edit`

Edits the details of an existing patient in your VitaBook.

Format: `edit INDEX [n/NAME] [g/GENDER] [h/HEIGHT] [w/WEIGHT] [no/PHONE] [e/EMAIL] [a/ADDRESS] [d/DIET] [pr/PRIORITY] [m/MEETING_DATE] [al/ALLERGY]…`

<box type="tip" seamless>

**Tips/Constraints:**
1. The index refers to the index number shown in the displayed patient list. The index **must be a positive integer**.

2. At least one field to edit must be provided.

3. Existing values will be updated to the input values.

4. You can remove all the patient’s allergies by typing `al/` without specifying any allergies after it.

5. The fields used in the `edit` command follow the same constraints as specified in the `add` command.
</box>

Examples:
*  `edit 1 no/91234567 e/johndoe@example.com` Edits the phone number and email address of the 1st patient (in the list) to be `91234567` and `johndoe@example.com` respectively.
*  `edit 2 n/Betsy Crower al/` Edits the name of the 2nd patient (in the list) to be `Betsy Crower` and clears all existing allergies.

<box type="warning" seamless>

**Warning:**
When editing allergies, the existing allergies will be replaced by the new ones you provide. To ensure that the old allergies are not deleted, make sure to include them in the `edit` command.
</box>

<br>

#### 2.1.4 Changing a Patient's Priority: `priority`

Changes a patient's priority by their index.

Format: `priority INDEX pr/PRIORITY`

<box type="tip" seamless>

**Tips/Constraints:**
1. The index refers to the index number shown in the displayed patient list. The index **must be a positive integer**.

2. Priority must be one of the following: `high`, `medium`, `low` (case-insensitive) and cannot be blank.
</box>

Examples:
* `priority 1 pr/HIGH` changes the priority of the 1st patient in the patient list to `HIGH`.

<br>

#### 2.1.5 Adding a Remark to a Patient: `remark`

Adds a new remark or replaces an existing remark of a patient.

Format: `remark INDEX r/[REMARK]`

<box type="tip" seamless>

**Tips/Constraints:**
1. You can use this command to add any conditions or custom information.

2. The index refers to the index number shown in the displayed patient list. The index **must be a positive integer**.

3. You can remove a patient's remark by typing `r/` without specifying any remarks after it.

4. You can add or edit exactly one remark for each patient.<br>
e.g. `remark 1 r/needs visual guides r/very motivated` will result in only the last remark `very motivated` updated as a remark to the specified patient.
</box>

<a href="images/multipleRemarksResult.png">

<img src="images/multipleRemarksResult.png" alt="result for 'remark 1 r/needs visual guides r/very motivated'" style="width: 100%; max-width: 700px; display: block;">
</a>

*Figure 3: Result when adding multiple remarks to a patient using `remark 1 r/needs visual guides r/very motivated`*

Examples:
* `list` followed by `remark 2 r/Enjoyed last week's meal plan, keep similar items` adds a remark to the 2nd patient in the patient list.
* `find Betsy` followed by `remark 1 r/Tends to skip meals when stressed` adds a remark to the 1st patient in the results list of the `find` command.
* `remark 3 r/` removes existing remark to the 3rd patient in the list.

<box type="warning" seamless>

**Warning:**
Remark command currently only supports adding a new remark or replacing an existing one. Thus, currently at most one remark can be displayed for each patient. Older remarks will be overwritten if you wish to add a new remark.
</box>

<br>

#### 2.1.6 Locating Patients by Name: `find`

Finds patients whose names contain *any* of the given **keywords**.

Format: `find KEYWORD [MORE_KEYWORDS]`

<box type="tip" seamless>

**Tips/Constraints:**
1. The search is case-insensitive.<br>
e.g `hans` will match `Hans`

2. The order of the keywords does not matter.<br>
e.g. `Hans Bo` will match `Bo Hans`

3. Only the name is searched.

4. Only full words will be matched.<br>
e.g. `Han` will not match `Hans`

5. Patients whose name matches any of the given keywords will be returned (i.e. `OR` search).<br>
e.g. `Hans Bo` will return `Hans Gruber`, `Bo Yang`
</box>

Examples:
* `find John` returns `john` and `John Doe`
* `find alex david` returns `Alex Yeoh`, `David Li`<br>

<a href="images/findAlexDavidResult.png">

<img src="images/findAlexDavidResult.png" alt="result for 'find alex david'" style="width: 100%; max-width: 700px; display: block;">
</a>

*Figure 4: Results for `find alex david`*

<br>

#### 2.1.7 Filtering Patients: `filter`

Filter patients based on a field (priority, diet, gender, meeting date).

Format: `filter pr/PRIORITY` or `filter d/DIET` or `filter g/GENDER` or `filter m/MEETING_DATE`

<box type="tip" seamless>

**Tips/Constraints:**
1. At least one field to filter must be provided.

2. The fields used in the `filter` command follows the same constraints as specified in the `add` command.
</box>

Examples:
* `filter pr/HIGH` returns all patients with high priority.
* `filter d/low sugar` returns all patients with low sugar diet.
* `filter g/f` returns all female patients.
* `filter m/2025-12-12` returns all patients with meeting date on `2025-12-12`.

<br>

#### 2.1.8 Sorting Patients: `sort`

Sorts patients based on specific criteria (priority, name, diet).

Format: `sort CRITERIA`

<box type="tip" seamless>

**Tips/Constraints:**
1. Criteria must be one of the following: `priority`, `name`, `diet` (case-insensitive) and cannot be blank.
</box>

Examples:
* `sort priority` returns the patient list sorted from the highest priority to the lowest priority.
* `sort name` returns the patient list sorted in lexicographical (alphabetical) order by name in ascending order.
* `sort diet` returns the patient list sorted in lexicographical (alphabetical) order by diet in ascending order.

<br>

#### 2.1.9 Deleting a Patient: `delete`

Deletes a patient from your VitaBook.

Format: `delete INDEX` or `delete EMAIL`

<box type="tip" seamless>

**Tips/Constraints:**
1. You can choose to delete the patient at the specified `INDEX`.

2. Alternatively, you can also delete the patient with a specified `EMAIL`.

3. The index refers to the index number shown in the displayed patient list. The index **must be a positive integer**.
</box>

Examples:
* `list` followed by `delete 2` deletes the 2nd patient in the patient list.
* `find Betsy` followed by `delete 1` deletes the 1st patient in the results list of the `find` command.
* `delete johnd@example.com` deletes the patient with email address `johnd@example.com`.

<br>

#### 2.1.10 Clearing all Patient Entries: `clear`

Clears all patient entries from your VitaBook.

Format: `clear`

<br>

### 2.2 To Provide a Convenient and Pleasant Experience

#### 2.2.1 Viewing Help: `help`

Opens a window with a link to this user guide.

Format: `help`

<a href="images/helpMessage.png">

<img src="images/helpMessage.png" alt="help message" style="width: 100%; max-width: 700px; display: block;"/>
</a>

*Figure 2: Window displaying the user guide link*

<br>

#### 2.2.2 Undoing the Last Change: `undo`

Undoes the last command that changed the patient list.

Format: `undo`

<box type="tip" seamless>

**Tips/Constraints:**
1. You can only undo for commands that changed the patient list (i.e. `add`, `edit`, `delete`, `remark`, `clear`, `priority`, `redo`).

2. Support multiple undo commands until the patient list reaches the initial state.
</box>

<br>

#### 2.2.3 Redoing the Last Undo: `redo`

Redoes the last undo.

Format: `redo`

<box type="tip" seamless>

**Tips/Constraints:**
1. You can only redo if you executed an undo command.

2. Support multiple redo commands until the patient list reaches the final state.
</box>

<box type="warning" seamless>

**Warning:**
Executing a new command that changes the patient list (excluding `undo`) after undo commands will purge the redo history. This means you cannot redo those undo commands anymore.
</box>

<br>

#### 2.2.4 Navigating through Command History: `↑` and `↓`

Navigates through the command history for quick access to previously executed commands.

Format: `↑` or `↓` arrow keys

<br>

#### 2.2.5 Toggling between Light Mode and Dark Mode

Transitions between light mode and dark mode for a more customisable and improved visual experience. Click the `File` menu to toggle between light mode and dark mode.

<a href="images/LightMode.png">

<img src="images/LightMode.png" alt="Light Mode Button" style="width: 100%; max-width: 700px; display: block;">
</a>

*Figure 5: Change from light mode to dark mode*

<a href="images/DarkMode.png">

<img src="images/DarkMode.png" alt="Dark Mode Button" style="width: 100%; max-width: 700px; display: block;">
</a>

*Figure 6: Change from dark mode to light mode*

<br>

#### 2.2.6 Exiting the Program: `exit`

Exits the program.

Format: `exit`

<br>

#### 2.2.7 Saving the Data

Your VitaBook data is saved in the hard disk automatically after any command that modifies the data. There is no need to save manually.

<br>

### 2.3 Bonus for Advanced Nutritionists

#### 2.3.1 Editing the Data File Directly!

Your VitaBook data is saved automatically as a JSON file `[JAR file location]/data/vitabook.json`. Advanced users are welcome to update data directly by editing that data file.

<box type="warning" seamless>

**Warning:**
If your changes to the data file makes its format invalid, VitaBook will discard all data and start with an empty data file at the next run.  Hence, it is recommended to take a backup of the file before editing it.<br>
Furthermore, certain edits can cause the VitaBook to behave in unexpected ways (e.g., if a value entered is outside the acceptable range). Therefore, edit the data file only if you are confident that you can update it correctly.
</box>

<br>

--------------------------------------------------------------------------------------------------------------------

## 3. FAQ

**Q**: What is VitaBook?
**A**: VitaBook is a desktop application designed for freelance nutritionists to manage patient information efficiently
using a typing-preferred interface. It is optimized for fast data entry and offline use.

**Q**: Who is VitaBook for?
**A**: VitaBook is for freelance or home-based nutritionists who need to track patient profiles, dietary
restrictions, medical notes, appointments, and reminders — all from a lightweight CLI application.

**Q**: How is VitaBook different from a regular address book?
**A**: In addition to basic contact details, VitaBook stores patient-specific information like gender, height, weight,
dietary tags, allergies, priority levels, and meeting dates. It’s tailored to healthcare use cases and offers structured patient management. Furthermore, VitaBook prevents data entry mistakes with robust input validation.

**Q**: Do I need to install any special software to run VitaBook?
**A**: You just need to have Java 17 installed. No other special software is required — simply run the JAR file.

**Q**: What kind of information can I store about a patient?
**A**: You can store the following information: name, phone, email, address, gender, height, weight, diet  (e.g., low sodium), meeting date, priority level, remarks and allergies (e.g., peanuts).

**Q**:What happens when I delete a patient?
**A**: All of their information (e.g. diet, priority, meeting date, medical notes etc.) will be deleted from your VitaBook. However, this can be recovered using the `undo` command.

**Q**: Can I undo a mistaken command?
**A**: Yes, you can! The `undo` command will undo the last command that changed the patient list.

**Q**: Can I add custom fields or conditions?
**A**: While you cannot add custom fields directly, you can use the 'remark' command to store additional information about a patient, such as conditions or other relevant notes. 

**Q**: Can I import data from another app or CSV file?
**A**: Not yet — but you can manually edit the JSON file (`data/vitabook.json`) to add patients if you're comfortable
with the format.

--------------------------------------------------------------------------------------------------------------------

## 4. Known Issues

- **Allergy fields are case-sensitive.**
  Adding allergies like `peanuts` and `Peanuts` results in two different allergies being stored. This can lead to duplicates or confusion when filtering/searching.

- **Allergy Validation is only alphanumeric.**
  User can enter any combination of letters and numbers, even if they don't represent actual allergies. This is because maintaining a complete list of all possible allergies is not feasible.

- **No support for recurring meeting dates or reminders.**
  Only a single meeting date can be stored per patient, with no repeat scheduling or notification support.

- **Commands must follow strict prefixes.**
  Forgetting a prefix (like `n/` for the name field) will result in an invalid command, even if the content is correct.

- **No concurrency or multi-user support.**
  VitaBook is designed as a single-user desktop application. Running two instances may cause file conflicts or data loss.

- **No graphical support for charts or health analytics.**
  Patient data is presented in text format only. Features like BMI calculation, graphs, or dashboards are not supported.

- **Application crashes if `vitabook.json` is manually corrupted.**
  If the user edits or corrupts the storage file manually, VitaBook may fail to start or load a blank state. To solve this issue, try deleting `vitabook.json` and rerunning the application. Remember to backup the file before deleting.
-------------------------------------------------------------------------------------------------------------------
[↑ Back to Top](#vitabook-user-guide)

## 5. Command Summary

Action        | Format, Examples
--------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
**Help**      | `help`
**Add**       | `add n/NAME g/GENDER h/HEIGHT w/WEIGHT no/PHONE e/EMAIL a/ADDRESS d/DIET pr/PRIORITY m/MEETING_DATE [al/ALLERGY]…`<br>e.g., `add n/Alex Yeoh g/M h/1.75 w/70 no/87438807 e/alex@example.com a/Blk 30 d/low sodium pr/LOW m/2025-12-12 al/peanuts`
**List**      | `list`
**Edit**      | `edit INDEX [n/NAME] [g/GENDER] [h/HEIGHT] [w/WEIGHT] [no/PHONE] [e/EMAIL] [a/ADDRESS] [d/DIET] [pr/PRIORITY] [m/MEETING_DATE] [al/ALLERGY]…`<br>e.g., `edit 1 d/low sugar w/68 pr/MEDIUM`
**Priority**  | `priority INDEX pr/PRIORITY`<br>e.g., `priority 2 pr/HIGH`
**Remark**    | `remark INDEX r/REMARK`<br>e.g., `remark 1 r/Likes protein-rich foods`
**Find**      | `find KEYWORD [MORE_KEYWORDS]`<br>e.g., `find Alex sugar`
**Filter**    | `filter pr/PRIORITY` or `filter d/DIET`  or `filter g/GENDER` or `filter m/MEETING DATE` <br>e.g., `filter d/low sodium`
**Sort**      | `sort CRITERIA `<br>e.g., `sort priority`
**Delete**    | `delete INDEX` or `delete EMAIL`<br>e.g., `delete 3` or `delete johnd@gmail.com`
**Clear**     | `clear`
**Undo**      | `undo`
**Redo**      | `redo`
**Navigate Command History** | `↑` or `↓` arrow keys
**Exit**      | `exit`

--------------------------------------------------------------------------------------------------------------------

## 6. Glossary

**Java 17**
The 17th version of the Java programming language and runtime environment.
Java 17 provides the libraries and tools necessary to run Java applications—such as VitaBook.

**JDK (Java Development Kit)**
A complete software development package that includes the Java runtime, compilers, and various tools to develop and run Java applications. Vitabook requires JDK 17 or later. Make sure you install the correct version to ensure compatibility.

**Terminal / Command Line Interface (CLI)**
A text-based interface used to interact with your computer’s operating system. In the terminal, you can navigate between folders and execute commands. To run Vitabook, open your terminal (or Command Prompt/PowerShell on Windows), use the `cd` command to navigate to the folder containing the `vitabook.jar` file, and then type:
```bash
java -jar vitabook.jar
```
<br>
--------------------------------------------------------------------------------------------------------------------
## 7. Java Setup Instructions

VitaBook requires **Java 17 or higher** to run.

<br>

### Check your Java version

Open a terminal or command prompt and run:
```
java -version
```
If Java is installed, you’ll see something like: `java version "17.0.9" 2024-01-16 LTS`.
If you see an error or a lower version, install Java 17 using the steps below.

<br>

### Install Java 17

[Installation Guide for Windows Users](https://se-education.org/guides/tutorials/javaInstallationWindows.html)<br>
[Installation Guide for Mac Users](https://se-education.org/guides/tutorials/javaInstallationMac.html)<br>
[Installation Guide for Linux Users](https://se-education.org/guides/tutorials/javaInstallationLinux.html)<br>


[↑ Back to Top](#vitabook-user-guide)<br>
[↑ Go to Quick Start](#quick-start)<br>
