# SOQL-APEX-

//SELECT Title, Name, Id, FirstName, LastName, Company, Email FROM Lead

//first way
//List<Lead> multilead1 =new List<Lead>();

/*second way
List<Lead> multiLead =[SELECT Title, Name, Id, FirstName, LastName, Company, Email FROM Lead];
System.debug(multilead);

for(Lead SingleLead:multiLead){
    System.debug(singleLead.firstname);
    System.debug(singleLead.lastname);
    System.debug('..........');
}

LeadApex.getLead('FL', 'farmers coop. of florida');*/


//first 20 of fibonacci numbers (0,1,1,2,3,5,8,13...)
/*Integer current;
Integer previous=1;
Integer beforePrevious=0;

System.debug(beforePrevious);
System.debug(previous);
Integer i=0;
while(i<18){
    current=previous+beforeprevious;
    System.debug(current);
    beforePrevious=previous;
    previous=current;
    i++;
}

List<Account> accList=[SELECT Id, Name FROM Account ORDER BY NAME];
for(integer x=0;x<accList.size();x++){
    system.debug(accList.get(x).Name);
}

accList.get(8).name='Deloitte';
update accList; // update diyerek DML fonksiyonu kullandik */


List<account> multiaccount=[SELECT Id, Name, Type,
(SELECT Id, Name, IsClosed, Type FROM Opportunities), 
(SELECT Id, Title, Name, Phone, Email, Department FROM Contacts)  FROM Account];

for(account singleAccount:multiaccount){
    System.debug(singleaccount.name+ singleaccount.type);
    
    for(contact singlecontact:singleaccount.contacts){
        System.debug(singlecontact.name);
        
        for(opportunity singleoppo:singleaccount.opportunities){
            system.debug(singleoppo.id);
        }
    }
}

