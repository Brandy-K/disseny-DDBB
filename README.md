# disseny-DDBB

## ENTITITES AND ATTRIBUTES
1. VENUE
venue_id- Identificador únic per a cada recinte.
Name- conté el nom del recinte.
stage m2- S'utilitza per salvar els metres quadrats de l'escenari.
spectator area m2- S'utilitza per salvar els metres quadrats de la zona d'espectadors.
max_capacity- Per guardar l'aforament màxim del recinte.
stage_covered- Conté atributs compostos per mostrar si l'escenari està cobert o no.
toilets- Conté atributs compostos per mostrar si el recinte té lavabos o no.

3. GROUP
   group id(primary key)- Conté un identificador únic que s'utilitza per identificar un grup.
   name- conté el nom del grup.
   country- Per mostrar els països d'on és cada grup.
   number of members- Quants membres hi ha en un grup.
   price- El preu que cobren per actuar en un concert. Es representa amb una el·lipse de punts perquè cada grup no cobra el mateix per     cada concert.

4. CONCERT PROGRAM
   group_id(foreign key)- Conté l'identificador del grup que actua en un recinte determinat.
   price- El preu cobrat pel concert.
   start day- El dia en què comença el concert.
   start time- L'hora en què comença el concert.
   end time- L'hora en què acaba el concert.

5. STREET
   street_code(primary key)- Conté el codi del carrer.
   name- Conté el nom del carrer.

6. PLOT
   plot_number(primary key)- Conté el número de parcel·la.
   street_code(foreign key)- Conté el codi del carrer on es troba la parcel·la. 
   ext.square meters- conté els metres quadrats de la parcel·la.
   price- Conté el preu de la parcel.la.

7.  ATTENDEES- conté informació sobre les persones assistents al festival.
    id(primary key)- Unique identifier for each attendee.
    username-  Unique username for each attendee.
    password- Emmagatzema la contrasenya dels assistents per accedir al compte.
    email- Conté l'adreça de correu electrònic dels assistents.
    firstname- Nom de l'assistent.
    lastname- Cognom de l'assistent.
    
9. RENTALS- conté informació sobre parcel·les de lloguer
   rental_id(primary key)- Identificador únic per a cada lloguer.
   plot_id(foreign key)-  Referència a la parcel·la llogada.
   manager_id(foreign key)- Reference to manager responsible.

10. MANAGER
   manager_id(primary key)-  Unique identifier for each manager.
   username- Username for the manager.

11. ACCESS (Associative for venue access)
    venue_id(foreign key)- Enllaça els registres d'accés al lloc.
    attendee_id(foreign key)- Enllaça el registre d'accés a l'assistent específic.
    access time- La data i l'hora en què l'assistent va accedir al recinte.

    ## RELATIONSHIPS
    One to Many:
    Venue and Concert Program- Each venue can host multiple concerts. The relationship is obligatory as each concert must be held in a venue.
    Group and Venue- One group can perfom at multiple venues at different times. The relationship is obligatory because each venue       requires at least one group to perfom.
    Group and Concert programs- One group can perfom at multiple concerts with a different price for each performance.
    Venue and attendees- One venue can have multiple attendees.This relationship is optional because not every attendee neeeds to access a venue.
    Street and plot- One street can have multiple plots.

    One to One:
    Plot and Rental pitch - One plot can only have one rental associated with it.
    Rental and Attendees- Only one attendee is responsible for each rental.
    Manager and Rentals- each manager is responsible for only one rental.

    Many to Many:
    Attendees and Venue- Each Venue can have multiple Attendees accessing it, and each Attendee can access multiple Venues. This is managed by the Access table.
    Venue and Group- Each Group can have multiple substitute groups, and each Group can act as a substitute for other groups. This is managed by the Replacement Group table
    
    
    
    
    
    
    
    
        

