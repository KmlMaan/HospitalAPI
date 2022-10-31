# HospitalAPI
Testing:
Doctor Registration :
![image](https://user-images.githubusercontent.com/114986701/199009910-aa30083e-14dd-4547-b96c-ef79840446fd.png)

Doctor Login :
![image](https://user-images.githubusercontent.com/114986701/199010049-546194b8-5183-4ae4-9970-82f107265631.png)

Paitent Registration :
![image](https://user-images.githubusercontent.com/114986701/199010168-105afada-4ccf-4548-8bbb-5dce9dfaf2c9.png)

Doctor can genrate the report like:
![image](https://user-images.githubusercontent.com/114986701/199010299-c38f1749-7ac9-47c4-a961-f990eb8370d6.png)


Fetching could be done by 
1. Phone number (by user or doctor)
![image](https://user-images.githubusercontent.com/114986701/199010490-b3810e96-9816-4987-8305-8dd3c6954455.png)


2. BY status of paitents (Only by doctor)
![image](https://user-images.githubusercontent.com/114986701/199010590-b4b05266-3b09-4714-8c03-f4f8c3382445.png)


Prerequistries:
1.MONGO DB
2.NODE JS
3.Postman


Basic Features:

    1.Register Doctor with username, password and name.
    2.Login(authenticate) User using passport-local and returns a jwt-token to be to access(authorize) protected routes.
    3.After logging-in the doctor can do various things such as : register patient, generate a report of patient, view all reports of a particular patient, filter all        the reports by status.
    4.Generation of report(protecte by jwt) : A doctor has to enter enter the status for a particular patient and can generate the report according to it.
    5.View all reports of a patient(protected by jwt) : A doctor can view all the reports of a patient.
    6.View all the reports filtered by status(protected by jwt) : A doctor can view all reports present in database filtered by status.
 
 
 
 
How to run :
    Start by installing npm and mongoDB if you don't have them already.
    Run the Mongo Server.
    Navigate to Project Directory by :

cd Hospital-API

    run following commands :

npm install 
npm start or node index.js




Working:

Base URL : http://localhost:8000/api/v1

1.
End Points :

    /doctor/register (POST) : Register a new doctor using 'name', 'username', 'password' and 'confirm-password' (all mandatory).
    Example input : (send name, username, password and confirm-password) 
    
2.
/doctor/login (POST) : login doctor using 'username' and 'password'.

Example input : (send username and password) 

3.
/patients/register (POST) :register patient using 'phone_number' and 'name' (phone number becomes id and will be used as it is).
Example input :

input form body: (send phone_number and name) 


4.
/patients/:id/create_report (POST) : create a report of a patient using ID (phone_number) sent in params and status.

Example input :

input form body: (send status, it is an enum which includes : [N,TQ,SQ,PA] which maps to [Negative, Travelled-Quarantine, Symptoms-Quarantine, Positive-Admit]


5.
/patients/:id/all_reports (GET) : Generate all reports of a patient by ID (phone_number) sent in params.


/reports/:status (GET) : Generate all reports in DB filtered by status sent in params.


status is an enum which includes : [N,TQ,SQ,PA] which maps to [Negative, Travelled-Quarantine, Symptoms-Quarantine, Positive-Admit]
