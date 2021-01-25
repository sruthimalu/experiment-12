# experiment-12
CREATE TABLE Sailors (sid int(6), 

sname varchar(20),rating int(6),age int(4),

PRIMARY KEY sid);

CREATE TABLE Boats (bid int(6), 

bname varchar (20), color varchar(10) 

PRIMARY KEY bid);

CREATE TABLE Reserves (sid int(6), 

bid int(6), day DATE, 

PRIMARY KEY (sid, bid, date), 

FOREIGN KEY sid REFERENCES Sailors,

FOREIGN KEY bid REFERENCES Boats);

 INSERT INTO Sailors  VALUES ('22','Manvi','7','45.0');

INSERT INTO Sailors  VALUES ('32','Mahi','8','55.0');

INSERT INTO Sailors  VALUES ('25','Ravi','10','35.0');

INSERT INTO Reserves VALUES ('22','101','7','10/10//98');

INSERT INTO Sailors  VALUES ('32','103','11/12/97');

INSERT INTO Boats VALUES ('101','red');

INSERT INTO Boats VALUES ('102','green');

INSERT INTO Boats VALUES('103','red);














SELECT A.SID , A.SNAME, A.RATING ,A.AGE

    FROM sailors AS A

    INNER JOIN reservers AS C ON A.SID =C.SID AND C.BID =101;

    

    SELECT B.BNAME

    FROM reserves AS C

    INNER JOIN sailors AS A ON A.SID =C.SID AND A.SNAME ='BOB'

    INNER JOIN boats AS B ON B.BID = C.BID;



    SELECT A.SNAME

    FROM sailors AS A

    INNER JOIN reserves AS C ON A.SID = C.SID

    INNER JOIN boats AS B ON B.BID = C.BID AND B.COLOR ='RED'

    ORDER BY A.AGE ;

    

	SELECT DISTINCT A.SNAME

    FROM sailors AS A 

    INNER JOIN reserves AS c ON A.SID IN (C.SID);

    

    SELECT A.SID , A.SNAME

    FROM reserves AS C

    INNER JOIN reserves AS D ON C.SID <> D.SID AND C.DAT =D.DAY

    INNER JOIN sailors AS A ON D.SID = A.SID;
