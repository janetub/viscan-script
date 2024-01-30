# ViscanScript

This project centers on the development of a web-based solution designed to enhance and streamline the thesis submission and binding procedures at the VSU Library. The current process faces challenges such as an inefficient queueing system, manual entry of details, manual receipt creation, and the need for manual retrieval of softcopies. Through this initiative, the project seeks to tackle these issues, ultimately improving the overall efficiency of material submission and automating the receipt generation process.

Target: VS.010.000

---
## Revisions

| **Revison Date**             | **Document Version**           | **Tracking Notes** | **Approved By** |
|--------------------------|----------------------------|----------------|-------------|
|                          |                            |                |             | 
|                          |                            |                |             |
|                          |                            |                |             |
|                          |                            |                |             |
|                          |                            |                |             |
|                          |                            |                |             |

---

## Program Function and Features

| **Functional Name**                                       | **Functional Requirement Description**                                                             |
|--------------------------------------------------------|------------------------------------------------------------------------------------------------|
| Provide an online form for data entry and file upload  | The system shall provide an online form that allows students to enter their name, student number, email address, course code, and thesis title.     |
| Validate the data and files entered by the student     | The system shall allow students to upload their softcopy requirements in PDF, Word, or JPG format, with a maximum file size of 100 MB each.          |
| Display an error or confirmation message upon form submission (Invalid/Incomplete Data) | The system shall display an error message if the student enters invalid or incomplete data, or uploads files that are not in the correct format or size. |
| Display a confirmation message upon form submission    | The system shall display a confirmation message and a summary of the data entered and the files uploaded when the student submits the form successfully. |
| Generate a unique priority number for each order        | The system shall generate a unique priority number for each student or order based on the date and time of form submission.                           |
| Store the order data and files in the database          | The system shall store the priority number, the data entered, and the files uploaded in the database, along with the status of the order (e.g., pending, reviewed, paid, completed, etc.). |
| Send an email to the student with their priority number and appointment details | The system shall use Nodemailer to send an email to the student with their priority number, along with the time and date of their appointment, within 24 hours of form submission. |
| Display the current priority number being served on a screen | The system shall display the current priority number being served on a screen in the library.                                                            |
| Access the order details by priority number             | The system shall allow the library staff to access the database and view the details of each order by priority number.                                    |
| Mark the order as checked or rejected and provide feedback or comments | The system shall allow the library staff to update the status of an order in the database after checking and confirmation, marking the order as checked or rejected, and provide feedback or comments if necessary. |
| Generate and print an acknowledgment receipt for each order | The system shall use a PDF library (PDFKit or pdfmake) in Node.js to generate a printable acknowledgment receipt for each order. |
| Update the payment status in the database               | The system shall allow the billing staff to update the payment status of an order in the database after receiving the payment.                             |
| Generate a printable binding order receipt for each order | The system shall use a PDF library (PDFKit or pdfmake) in Node.js to generate a printable a binding order receipt for each order.                          |
| Confirm that the order is complete and ready for claiming | The system shall allow the library staff to confirm that the order is complete and ready for claiming by the student.                                       |
| Send an email to the student notifying them that their order is ready for pickup | The system shall use Nodemailer to send an email to the student notifying them that their order is ready for pickup, along with the date and time of claiming. |
| Update the order status in the database as completed    | The system shall allow the library staff to update the order status in the database as completed.                                                          |

---

## Provide an online form for data entry and file upload
### Online Form
This is used to collect the student’s information and softcopy requirements for thesis submission and binding.
#### Input
The student shall fill in the online form with their name, student number, email address, course code, thesis     title, and number of copies.
#### Process
- The user shall initiate the data entry process.
- The system shall provide fields for the user to enter their name, student number, email address, course code, and thesis title.
- The student shall upload two e-copy or softcopy of the manuscript, one in PDF and one in Word format.
- The student shall upload one file of 2-by-2 ID picture in JPG or JPEG format.
- The student shall choose an appointment date from the available dates.
- The user shall submit the form after entering the required information.
#### Output
The online form is submitted and the data and files are stored in the database.

---

## Validate the data and files entered by the student
### Data and File Validation
This is used to ensure that the student enters valid and complete data and uploads files that are in the correct format and size.
#### Input
The student shall enter the data and upload the files in the online form.
#### Process
- The system shall check the data entered by the student for completeness and validity.
- The system shall check the files uploaded by the student for format and size.
- The system shall display an error message if the data or files are invalid or incomplete.
#### Output
The data and files are validated and the student is informed of the result.

---

### Display an error or confirmation message upon form submission
### Error Message Display
This is used to inform the student if there are any errors in their submission
#### Input
The system shall check the data and files entered by the student.
#### Process
- The system shall display an error message if the student enters invalid or incomplete data, or uploads files that are not in the correct format or size.
#### Output
This is used to confirm the successful submission of the form.

### Confirmation Message Display
This is used to inform the student if there are any errors in their submission
#### Input
The system shall check the data and files entered by the student.
#### Process
- The system shall display a confirmation message and a summary of the data entered and the files uploaded when the student submits the form successfully.
#### Output
The confirmation message is displayed.

---

### Generate a unique priority number for each order
### Priority Number Generation
This is used to assign a unique priority number to each student or order based on the date and time of form submission.
#### Input
The student shall enter the data and upload the files in the online form.
#### Process
- The system shall generate a unique priority number for each student or order using a sequential number algorithm, which starts with 1 as the first number and adds 1 to the previous number to get the next number.
- The system shall store the priority number in the database along with the data and files.
- The system shall send an email to the student with their priority number and appointment details.
#### Output
The priority number is generated and the student is notified by email.

---

### Store the order data and files in the database
### Order Data and File Storage
This is used to store the order data and files in the database for future reference and processing.
#### Input
The student shall submit the online form with their data and files.
#### Process
- The system shall store the priority number, the data entered, and the files uploaded in the database, along with the status of the order (e.g., pending, reviewed, paid, completed, etc.).
#### Output
The order data and files are stored in the database.

---

### Send an email to the student with their priority number and appointment details
### Appointment Email Notification
This is used to notify the student about their priority number and appointment details via email.
#### Input
The student shall submit the online form with their data and files.
#### Process
- The system shall use Nodemailer to send an email to the student with their priority number, along with the time and date of their appointment, within 24 hours of form submission.
#### Output
The appointment details are sent to the student via email.


---

## Data Dictionary

| **Element ID**               | **Element Text**               | **Element Type**  | **Data Type** | **Required?** | **Rules**                                           |
|--------------------------|----------------------------|---------------|-----------|-----------|-------------------------------------------------|
| NameField                | Name                       | Text          | Text      | Yes       | -                                               |
| StudentNumberField       | Student Number             | Text          | Text      | Yes       | -                                               |
| EmailAddressField        | Email Address              | Text          | Text      | Yes       | -                                               |
| CourseCodeField          | Course Code                | Text          | Text      | Yes       | -                                               |
| ThesisTitleField         | Thesis Title               | Text          | Text      | Yes       | -                                               |
| NumberOfCopiesField      | Number of Copies           | Number        | Numeric   | Yes       | -                                               |
| WordECopyUploadButton    | Upload Word eCopy          | Button        | -         | Yes       | To upload a Word eCopy, the user must be logged in |
| PDFECopyUploadButton     | Upload PDF eCopy           | Button        | -         | Yes       | To upload a PDF eCopy, the user must be logged in  |
| IDPhotoUploadButton      | Upload ID Photo            | Button        | -         | Yes       | To upload an ID photo, the user must be logged in |
| AppointmentDateField     | Select Appointment Date    | Date Picker   | Date      | Yes       | -                                               |
| PriorityNumberTile       | Priority Number            | Text          | Text      | -         | -                                               |
| ThesisTitleTile          | Thesis Title               | Text          | Text      | -         | -                                               |
| OrderStatusTile          | Order Status               | Text          | Text      | -         | -                                               |
| SelectedOrderPreview     |                            |               |           |           |                                                 |

---
