607WEEK8ASSIGNEMT
=================
Dieudonne ouedraogo

#(1) url  :http://blogs.wsj.com/?mod=WSJ_formfactor


-- Database: "WSJBLOGS"



-- DROP DATABASE "WSJBLOGS";

CREATE DATABASE "WSJBLOGS"
  WITH OWNER = postgres
       ENCODING = 'UTF8'
       TABLESPACE = pg_default
       LC_COLLATE = 'English_United States.1252'
       LC_CTYPE = 'English_United States.1252'
       CONNECTION LIMIT = -1;
       
       -- Table: "POSTS"

-- DROP TABLE "POSTS";

CREATE TABLE "POSTS"
(
  "PostID" integer NOT NULL,
  "Title" character varying(100) NOT NULL,
  "Content" character varying(200),
  "Blogger" character varying(100),
  "PostDate" date NOT NULL,
  CONSTRAINT "ID" PRIMARY KEY ("PostID")
)
WITH (
  OIDS=FALSE
);
ALTER TABLE "POSTS"
  OWNER TO postgres;
  
-- Table: "COMMENTS"

-- DROP TABLE "COMMENTS";

CREATE TABLE "COMMENTS"
(
  "PostID" integer NOT NULL,
  "CommentID" integer NOT NULL,
  "CommentAuthor" character varying(100) NOT NULL,
  "CommentContent" character varying(200),
  "CommentDate" date NOT NULL,
  CONSTRAINT "CommentID" PRIMARY KEY ("CommentID"),
  CONSTRAINT "ID" FOREIGN KEY ("PostID")
      REFERENCES "POSTS" ("PostID") MATCH SIMPLE
      ON UPDATE NO ACTION ON DELETE NO ACTION
)
WITH (
  OIDS=FALSE
);
ALTER TABLE "COMMENTS"
  OWNER TO postgres;
  
  -- Table: "TAGS"

-- DROP TABLE "TAGS";

CREATE TABLE "TAGS"
(
  "PostID" integer NOT NULL,
  "TagType" character varying(100),
  CONSTRAINT "TagID" PRIMARY KEY ("PostID"),
  CONSTRAINT "ID" FOREIGN KEY ("PostID")
      REFERENCES "POSTS" ("PostID") MATCH SIMPLE
      ON UPDATE NO ACTION ON DELETE NO ACTION
)
WITH (
  OIDS=FALSE
);
ALTER TABLE "TAGS"
  OWNER TO postgres;
  
  INSERT INTO "POSTS"(
            "PostID", "Title", "Content", "Blogger", "PostDate")
    VALUES (1,'Cost Of War Against ISIS So Far:','The Pentagon is spending $7.6 MILLION a day..','DION NISSENBAUN','2014-10-21');
    
    INSERT INTO "TAGS"(
            "PostID", "TagType")
    VALUES (1,'Washington Wire');
    
    INSERT INTO "COMMENTS"(
            "PostID", "CommentID", "CommentAuthor", "CommentContent", "CommentDate")
    VALUES (1,1,'Dieudonne Ouedraogo','I hope this time we have a clear vision and we wont engage in years battle','2014-10-21');
    
    INSERT INTO "POSTS"(
            "PostID", "Title", "Content", "Blogger", "PostDate")
    VALUES (2,'FBI Agent in Abscam Sting to Campaign for Pressler in South Dakota ','In South Dakota, former FBI agent John Good is joining Larry Pressler on the campaign trail to highlight the former senator’s  honesty during the Abscam inquiry in the late 1970s and early 1980s...','Kristina Peterson','2014-10-21');
    
    INSERT INTO "TAGS"(
            "PostID", "TagType")
    VALUES (2,'Washington Wire');
    
    INSERT INTO "COMMENTS"(
            "PostID", "CommentID", "CommentAuthor", "CommentContent", "CommentDate")
    VALUES (2,2,'Dieudonne Ouedraogo','wow ,interesting way of campaign','2014-10-21');


    
    
INSERT INTO "POSTS"(
            "PostID", "Title", "Content", "Blogger", "PostDate")
    VALUES (3,'Facebook Sues Lawyers for Allegedly Contributing to Fraud  ','Facebook is suing several law firms that represented a man who claimed he owned half of the social network and was entitled to billions of dollars from the company and its CEO Mark Zuckerberg..','Jacob Gershman ','2014-10-20');
    
    INSERT INTO "TAGS"(
            "PostID", "TagType")
    VALUES (3,'LAW BLOG ');
    
    NSERT INTO "COMMENTS"(
            "PostID", "CommentID", "CommentAuthor", "CommentContent", "CommentDate")
    VALUES (3,6,'BARBARA ORTUTAY','Facebook launched in February 2004 out of Zuckerbergs Harvard dorm room. It was first open only to Harvard students since it expanded into the world  more than 1.3 billion users.','2014-10-21');






  
  
  


       

