# SQL 

## Table Creation
```
create table userr(
  user_id int primary key,
  username varchar(255) not null,
  password varchar(255) not null,
  role varchar(255) default 'user' check (role in ('user','admin'))
);
```

```
create table artwork (
  aw_id int primary key,
  aw_title varchar(255) not null,
  aw_hearts int default 10 check (aw_hearts>=0),
  aw_downloads int default 10 check (aw_downloads>=0)
);
```

```
create table ratings (
  rating_id int primary key,
  user_id int,
  aw_id int,
  rating int check (rating between 0 and 5),
  foreign key (user_id) references userr(user_id) on delete cascade,
  foreign key (aw_id) references artwork(aw_id) on delete cascade
);
```

```
create table comments(
  comment_id int primary key,
  user_id int,
  aw_id int,
  foreign key (user_id) references userr(user_id),
  foreign key (aw_id) references artwork(aw_id)
);
```

```
create table downloads(
  download_id int primary key,
  user_id int,
  aw_id int,
  foreign key (user_id) references userr(user_id),
  foreign key (aw_id) references artwork(aw_id)
);
```

```
create table user_profile(
  profile_id int primary key,
  user_id int,
  bio varchar(255) default '',
  foreign key (user_id) references userr(user_id)
);
```

## Trigger
```
CREATE OR REPLACE TRIGGER Enforce_Title_Integrity
BEFORE INSERT OR UPDATE ON artwork
FOR EACH ROW
BEGIN
  --Simple words added
  IF INSTR(LOWER(:New.aw_title), 'banned')>0 OR
     INSTR(LOWER(:NEW>aw_title), 'inappropriate')>0 THEN
   RAISE_APPLICATION_ERROR(-20003, 'Contains Prohibited Words.');
  END IF;
END;
```

## Procedure
```
CREATE OR REPLACE PROCEDURE Add_Art (
  a_aw_id in int,
  a_aw_title in varchar,
  a_aw_hearts in int,
  a_aw_downloads in int
) IS
BEGIN
  IF a_aw_hearts<0 OR a_aw_downloads<0 THEN
    RAISE_APPLICATION_ERROR(-20001, 'Hearts or Downloads should be a Positive Value');
  END IF;

  INSERT INTO artwork (aw_id, aw_title, aw_hearts, aw_downloads)
  VALUES (a_aw_id, a_aw_title, a_aw_hearts, a_aw_downloads);

  COMMIT;
END;
```

## Package
```
CREATE OR REPLACE PACKAGE Artwork_Management AS
  PROCEDURE Add_Artwork (
    a_aw_id in int,
    a_aw_title in varchar,
    a_aw_hearts in int,
    a_aw_downloads in int
  );
  PROCEDURE Update_Artwork_title (
    a_aw_id in int,
    a_aw_title in int
  );
  PROCEDURE Delete_Artwork (
    a_aw_id in int
  );
END  Artwork_Management;
```




