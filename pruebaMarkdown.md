# -- Hello Markdown! --
My name is Gabriel Landín. I am a beginner for Markdown
I 've just tried this [Markdown for Absolute Beginners using Visual Studio Code.](https://www.youtube.com/watch?v=UvaZzOkM1j0)

I hope you enjoy this session.

### PostGIS Example 
```c
-- Drop the table in case it exists
DROP TABLE IF EXISTS chp02.xwhyzed CASCADE;
CREATE TABLE chp02.xwhyzed
-- This table will contain numeric x, y, and z values
(
x numeric,
y numeric,
z numeric
)
WITH (OIDS=FALSE);
ALTER TABLE chp02.xwhyzed OWNER TO me;
-- We will be disciplined and ensure we have a primary key
ALTER TABLE chp02.xwhyzed ADD COLUMN gid serial;
ALTER TABLE chp02.xwhyzed ADD PRIMARY KEY (gid);
```
### More PostGIS
```c
INSERT INTO chp02.xwhyzed (x, y, z)
VALUES (random()*5, random()*7, random()*106);
INSERT INTO chp02.xwhyzed (x, y, z)
VALUES (random()*5, random()*7, random()*106);
INSERT INTO chp02.xwhyzed (x, y, z)
VALUES (random()*5, random()*7, random()*106);
INSERT INTO chp02.xwhyzed (x, y, z)
VALUES (random()*5, random()*7, random()*106);
```
Markdown is simple but powerful way to make documentation for you code. 
You can learn more about Markdown from [Markdown - La guía definitiva en español](https://markdown.es/).

The imagen of Markdown and PostGIS.

![The imagen of Markdown](https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/Markdown-mark.svg/640px-Markdown-mark.svg.png)

![PostGIS](https://i1.wp.com/acolita.com/wp-content/uploads/2017/10/Que-es-PostGIS.jpg?fit=640%2C400&ssl=1)

### more PostGIS.
```c
-- Ensure we don't try to duplicate the view
DROP VIEW IF EXISTS chp02.xbecausezed;

-- Retain original attributes, but also create a point attribute from x and y
CREATE VIEW chp02.xbecausezed AS
SELECT x, y, z, ST_MakePoint(x,y)
FROM chp02.xwhyzed;

-- Ensure we don't try to duplicate the view
DROP VIEW IF EXISTS chp02.xbecausezed;

-- Retain original attributes, but also create a point attribute from x and y
CREATE VIEW chp02.xbecausezed AS
SELECT x, y, z, ST_SetSRID(ST_MakePoint(x,y), 3734) -- Add ST_SetSRID
FROM chp02.xwhyzed;
```