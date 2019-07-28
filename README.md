# AxiosProject

-- Table: applications

-- DROP TABLE applications;

CREATE TABLE applications
(
  app_id integer NOT NULL DEFAULT nextval('"Applications_app_id_seq"'::regclass),
  app_name character varying,
  app_status character varying,
  application_age integer,
  handled_by character varying,
  cust_id integer,
  CONSTRAINT "Applications_pkey" PRIMARY KEY (app_id),
  CONSTRAINT "Applications_cust_id_fkey" FOREIGN KEY (cust_id)
      REFERENCES customers (cust_id) MATCH SIMPLE
      ON UPDATE NO ACTION ON DELETE NO ACTION
)
WITH (
  OIDS=FALSE
);
ALTER TABLE applications
  OWNER TO postgres;
