# MIST4610Project
## Team Name:
The Dream Team

## Team Members:
1. Andrew Neely [@AndrewN2024](https://github.com/AndrewN2024)
2. Carter Johnson [@C0John](https://github.com/C0John)
3. Nate Jarrow [@NateJ123](https://github.com/NateJ123/)
4. Andrew Zhang [@drewteriyaki](https://github.com/drewteriyaki)
5. Mark Zhang [@zhmark9](https://github.com/zhmark9)
   
## Problem Description
Our client has tasked us with modeling the internal database of their urgent medical care facility. The facility provides emergency services that do not require a trip to a hospital emergency room, as well as regular scheduled appointments to patients. The facility is regularly staffed by multiple physicians and nurses. Physicians may prescribe and administer medication, and patients may be covered by insurance and provide feedback on the service(s) they received. Our team’s objective is to design the relational database around these aspects of the client’s business, taking into account how each entity interacts with each other. We are interested in accurately modeling these relationships as well as providing completed sample data. The database is also meant to keep track of their day-to-day operations and provide useful insights into trends, demographics, and other analytics. 

## Data Model:

Our model is based on a hypothetical scenario involving modeling a database for an emergency healthcare clinic. The patient entity contains a unique ID along with basic identifying information about the patient (including contact information). The patient entity has a relationship with many entities which are the insurance provider entity, appointment entity, prescription entity, billing entity, feedback entity, medical history entity, and lab test entity. A patient can have one insurance provider, but an insurance provider can provide for many people therefore there is a one-to-many relationship between the two. We have an insurance provider entity that contains basic information about the insurance provider and a unique ID to identify each provider. The patient entity has a one-to-many relationship with the billing entity because a particular patient can have various bills associated with different visits to the clinic. This entity includes basic billing information such as the services provided and the date of the service along with a unique identifier. Another one-to-many relationship the patient entity has is with feedback because a customer can send in multiple feedback surveys, but each feedback survey can only come from one person. The feedback entity has the date, survey questions, rating, comments, patient ID (FK), and a unique identifier for each feedback. A patient can also have many different medical histories (or records) so there is a one-to-many relationship between the two entities. The medical history entity contains the date of the visit, medical conditions, allergies, previous treatments, and a patient ID. The unique identifier for the medical history table is a combination of the date of visit and patient ID. Also, staff can run many lab tests on a patient which constitutes a one-to-many relationship between the patient entity and the lab test entity. The lab test entity contains the test name, date, results, patient ID(FK), and a unique identifier for each lab test.

The prescription entity and appointment entity are associative entities that connect the patient entity with the staff entity to make two many-to-many relationships. That means their relationship with the patient entity is technically one-to-many. A patient can have many prescriptions, but a singular prescription has to be attributed to one patient. Additionally, a patient can have many appointments, but a singular appointment is only booked for one person.

The appointment entity has information about each appointment such as the diagnosis, treatment, reason for visit, date of visit, diagnosis, treatment, facility ID (FK), patient ID (FK), staff ID (FK), time of visit, and a unique identifier for each appointment. The appointment entity has a few relationships with other entities as well. It has its relationship with both staff and patient by acting as the associative entity to create a many-to-many relationship between the two. Also, it has a many-to-many relationship with the medication entity which is connected through an associative entity called medication administered which has its own unique ID. Finally, it has a many-to-one relationship with the facility entity because a facility can host many appointments, but an appointment can only be held at one facility. The facility entity has the facility address, name, phone number, operating hours, and a unique identifier for each facility.

The prescription entity also acts as the associative entity between staff and patient and has a many-to-one relationship with medication. This means that a medication can be a part of many different prescriptions, but a prescription can only be tied back to a singular medication. The prescription entity contains dosage instructions, the issue date, the patient ID (FK), the medication ID (FK), the staff ID (FK), and a unique identifier for each prescription.

The staff entity has one final relationship along with its relationship to patient through appointment and prescription which is its many-to-many relationship with the shift entity. A staff can have many shifts and a shift can contain multiple staff. The associative entity that connects the two is called staff_working and has its own unique identifier along with the primary keys of staff and shift. The staff entity contains basic contact information, personal information, certifications, and a staff member’s schedule along with a unique identifier for each staff member. The shift entity contains the start time, end time, date, location, and a unique shift identifier. 

![image](https://github.com/C0John/MIST4610Project/assets/148258373/f9e6a48c-30e1-4b73-841c-6b901e83d04d)


## Data Dictionary:

![image](https://github.com/C0John/MIST4610Project/assets/148258373/a1051e74-86ab-416e-acc4-06762ffe1780)

![image](https://github.com/C0John/MIST4610Project/assets/148258373/e9c4042e-99bf-484b-aa6c-5ddc22e156eb)

![image](https://github.com/C0John/MIST4610Project/assets/148258373/c01f9afd-f3a5-488e-9cfc-a0386a5b7294)

![image](https://github.com/C0John/MIST4610Project/assets/148258373/652fa068-722f-48d4-b23c-755ba1c575be)

![image](https://github.com/C0John/MIST4610Project/assets/148258373/bc4ebeac-855e-4828-b555-6e9b5d9a467c)

![image](https://github.com/C0John/MIST4610Project/assets/148258373/4e4f0a3e-6461-48ef-bb01-2cc05534813f)

![image](https://github.com/C0John/MIST4610Project/assets/148258373/786b8e94-a70c-43ba-ac0a-bc00ce63b5cf)

![image](https://github.com/C0John/MIST4610Project/assets/148258373/814b8ccc-a142-428e-af5f-19cf7c1236dc)

![image](https://github.com/C0John/MIST4610Project1/assets/148258373/956728c6-f650-4af2-b49f-4d70232e0faa)

![image](https://github.com/C0John/MIST4610Project1/assets/148258373/84cb31cc-bb90-49d4-a7a8-b61666187ab3)

![image](https://github.com/C0John/MIST4610Project/assets/148258373/26c0fd28-73c2-43f8-85f0-94608dd5e357)

![image](https://github.com/C0John/MIST4610Project/assets/148258373/ee417fb6-d101-4f63-9168-d387ae67cca0)

![image](https://github.com/C0John/MIST4610Project/assets/148258373/56fa7ee3-4ad5-4676-ae4d-e70aee9a9d89)

![image](https://github.com/C0John/MIST4610Project/assets/148258373/6e118308-392e-4788-9ff2-5b8359f0f77e)


## Queries

![image](https://github.com/C0John/MIST4610Project1/assets/148258373/1d0899d6-e1ea-42e4-99cd-f01a883a2461)

### Query 1 (Complex)
Query 1 lists the total revenue for each insurance provider during a specific date range. The results were grouped by the name of the Insurance Provider.
### Justification:
Query 1 provides managers insights into the financial performance of each provider during a set period and helps managers make informed decisions. By understanding which providers brings in the most revenue, managers can allocate resources to effectively meet patient needs.

![image](https://github.com/C0John/MIST4610Project/assets/149621626/d67f3418-b5df-4044-a10a-202ea42d0138)

### Query 2 (Complex)
Query 2 lists the name of the patients who have had the highest number of appointments. The results are grouped by patient name where the patient with the highest number of appointments is listed.
### Justification:
Query 2 allows managers to see which patients visit the healthcare facility most frequently. This information is valuable to managers because it can help them recoginize and appreicate loyal patients who regularly seek care, assist in resource allocation, and ensure that the facility's staff and equipment cater to the needs of these engaged patients.

![image](https://github.com/C0John/MIST4610Project/assets/149621626/12ae21a5-d944-471c-8fa6-2ebc3447845f)

### Query 3 (Simple)
Query 3 lists all prescription records, including the patient's name, prescribed medication, dosage, and the issuing staff member.
### Justification:
Query 3 allows managers to have a retained prescription history along with patient and staff information. Some instances where managers may need this information is for billing purposes, if a patient changes providers and needs records transferred, patient safety, overall facility accountability, and even research purposes.

![image](https://github.com/C0John/MIST4610Project/assets/149621626/005be857-d845-4fb8-bdc9-aa9a468523f1)

### Query 4 (Complex)
Query 4 lists the ID, name, and job title of each staff member, along with their financial contribution based on appointments. The results are ordered by total revenue generated in descending order. 
### Justification:
Query 4 allows managers to assess the revenue generated for each staff member. Managers can use this information to have insight into the performance, contribution of staff members, and to allocate resources.

![image](https://github.com/C0John/MIST4610Project/assets/148258373/bee38b19-54c2-4abe-bb41-ee65cf1dabb1)

### Query 5 (Simple)
Query 5 lists patients and their insurance providers, with the name and contact information for both parties.
### Justification:
Query 5 allows managers to have updated contact information for both patients and the insurance providers for said patients in order to keep track of administrative and billing responsibilities. This query allows managers to keep track of the contact details of both parties and provides managers with quick access to this information.

![image](https://github.com/C0John/MIST4610Project/assets/148258373/3a472f7b-2ae4-4f2c-a3d5-5003dcdeec82)

### Query 6 (Complex)
Query 6 allows pharmacist and doctors to find Robert Lee’s assigned prescription information that will be printed onto the bottle (instructions, medication name, dosage, expiration date, issue date, and staff name).
### Justification:
Query 6 allows managers to find prescription information for a particular patient (in this case, Robert Lee) and the information associated with the prescription. It provides managers the ability to keep track of individual patient's information. For example, pulling a distinct record during an appointment instead of sifting through all patient data.

![image](https://github.com/C0John/MIST4610Project/assets/148258373/6800f5ad-41db-44cb-81c5-a23b022903d1)

### Query 7 (Complex)
Query 7 allows the hospital to view male patient feedback and ratings that are male and are between the ages of 23 and 33.
### Justification:
Query 7 allows managers to keep track of feedback from males in the age bracket of 23 and 33. This particular insight can provide managers with ways to improve staff to patient relationships, assess patient satisfaction in this age and gender bracket, and other important information.

![image](https://github.com/C0John/MIST4610Project/assets/148258373/524ce1ef-651b-4afd-83d8-733df7796579)

### Query 8 (Simple)
Query 8 lists the names of all staff members, shift location, and their shift start/end on 11/03/2023.
### Justification:
Query 8 allows managers to keep track of staff members' shifts and their names. Managers can use this information to keep track of which staff members works where and when they started or ended. In addition, they can plan scheduling, allow for planning for busy days or emergencies, pay, and keeping up with legal aspects of employment.

![image](https://github.com/C0John/MIST4610Project/assets/148258373/bc80e288-8298-4c56-b63f-d66ca1028e7c)

### Query 9 (Simple)
Query 9 returns a list of all bills from before 2023-11-30 that are still unpaid and the relevant data of each particular bill.
### Justification:
Query 9 allows managers to keep track of bills that are still unpaid from a specific date and prior (in this case 2023-11-30), which could enable managers to send out a reminder to the related patients who have yet to pay their bill(s). In addition, managers could use this information to assess financial stability, status, billing errors, and financial planning.

![image](https://github.com/C0John/MIST4610Project/assets/148258373/afd80767-a76d-4732-8d6b-196318982e0c)

### Query 10 (Complex)
Query 10 returns a list of patients under the age of 70 who have had at least one appointment with the hospital, along with their age using a math formula. It also orders the results in descending order by the number of appointments each patient has had.
### Justification:
Query 10 allows managers to see the age of each patient and how it corresponds with the number of appointments the patient has had. This can be useful for recording demographics of the clinic's patients and running analytics. Additionally, the query is easily modifiable to look for patients of different age ranges, or patients with more than a certain number of appointments. 

![image](https://github.com/C0John/MIST4610Project/assets/148258373/30fcc3be-297b-451d-a4c0-f6e73af08585)

## Database Information:
Name of the database: cs_g6p1
- Each query listed above is marked in the database using stored procedures which can be called using the following format: CALL Q1();




