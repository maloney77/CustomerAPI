Requirements for this coding challenge 


The requirements for the test project are:
Mulesoft:
Customer Management
The client needs REST APIs to handle a few incoming/outcoming client information and store it in CSV files for another system to consume.
You’ll need to create two different folders for this project, one for testing purposes that can be called testing and another folder for production. The files should be named Customers-QA and Customers-PRD respectively.
Expected headers for the customer: Client Key, First Name, Middle Name, Last Name, BirthDate, Height, Weight, Billing Street, Billing City, Billing State, Billing Postal Code, Billing Country, Created Date.
The first REST API is going to receive a new client inside a JSON body and will create this new record in the csv file:
- The new record is going to be added as the last row in an existing file. In case the CSV file was not created yet, it should be created with the header populated and the new record as the second row.
- The created date should be populated automatically with the current server datetime. 
- Both Birth Date and Created Date need to be saved in the file as a Java Long data type (e.g. 1543795200000)
- Create a random key to associate with the Client Key column
- First Name, Last Name, and Birth Date are mandatory information and an error message should be thrown in case one of them is not populated.
- If the new record was successfully saved, you should return the client key generated and the proper HTTP status.
The second REST API should retrieve all the information from the CSV file, convert it to JSON and return the list of clients to its consumer.
- In case there are no file or no records inside the folder, please return an error message in the JSON format and the proper HTTP status.
- At the end of the JSON response, please add the total number of records found inside the CSV file.
- The Birth Date/Created Date should be converted and returned in the following format: DD.MM.YYYY
- The fields Billing Street, Billing City, Billing State, Billing Postal Code and Billing Country should all be concatenated and returned as “Billing Address”
The third REST API should delete an entire row inside the csv file:
- Receive the client key as a query parameter.
- Look for the client key inside the CSV and update the file deleting the entire client row and returning a success message with the proper HTTP status.
- Return an error message and the proper HTTP status in case the client was not found inside the csv file.
Some considerations:
- Both the names of the folders and the files should be stored dynamically inside two different mule properties because they are often updated by the client.
- Don’t forget to handle the exceptions for each flow and return the proper HTTP status.
- Create a MUNIT flow with full testing coverage for this project.
- This project can be built with any Mule version as long as it respects these requirements.
- Keep in mind that you’ll need to present all the three APIs working as expected by consuming them at the time of the interview.
