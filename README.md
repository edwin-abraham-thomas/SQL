# SQL
SQL learning resources to postgres database

## Setup Dataset
1. Create database
    ```sql
    CREATE DATABASE airlines WITH TEMPLATE = template0 ENCODING = 'UTF8' LC_COLLATE = 'C' LC_CTYPE = 'C';
    ALTER DATABASE airlines OWNER TO postgres;
    ```
2. Create tables
    ```sql
    --
    -- Name: codes_cancellation; Type: TABLE; Schema: public; Owner: postgres
    --  
    CREATE TABLE IF NOT EXISTS public.codes_cancellation (
        cancellation_code character varying(2),
        cancel_desc character varying(45)
    );
    ALTER TABLE public.codes_cancellation OWNER TO postgres;

    --
    -- Name: codes_carrier; Type: TABLE; Schema: public; Owner: postgres
    --  
    CREATE TABLE IF NOT EXISTS public.codes_carrier (
    carrier_code character varying(2),
    carrier_desc character varying(45)
    );  
    ALTER TABLE public.codes_carrier OWNER TO postgres;

    --
    -- Name: perform_feb; Type: TABLE; Schema: public; Owner: postgres
    --  
    CREATE TABLE IF NOT EXISTS public.perform_feb (
        fl_date date,
        mkt_carrier character varying(2),
        mkt_carrier_fl_num character varying(4),
        origin character varying(3),
        origin_city_name character varying(45),
        origin_state_abr character varying(2),
        dest character varying(3),
        dest_city_name character varying(45),
        dest_state_abr character varying(2),
        dep_delay_new numeric,
        arr_delay_new numeric,
        cancelled numeric,
        cancellation_code character varying(2),
        diverted numeric,
        carrier_delay numeric,
        weather_delay numeric,
        nas_delay numeric,
        security_delay numeric,
        late_aircraft_delay numeric
    );  
    ALTER TABLE public.perform_feb OWNER TO postgres;

    --
    -- Name: performance; Type: TABLE; Schema: public; Owner: postgres
    --  
    CREATE TABLE IF NOT EXISTS public.performance (
        fl_date date,
        mkt_carrier character varying(2),
        mkt_carrier_fl_num character varying(4),
        origin character varying(3),
        origin_city_name character varying(45),
        origin_state_abr character varying(2),
        dest character varying(3),
        dest_city_name character varying(45),
        dest_state_abr character varying(2),
        dep_delay_new numeric,
        arr_delay_new numeric,
        cancelled numeric,
        cancellation_code character varying(2),
        diverted numeric,
        carrier_delay numeric,
        weather_delay numeric,
        nas_delay numeric,
        security_delay numeric,
        late_aircraft_delay numeric
    );  
    ALTER TABLE public.performance OWNER TO postgres;
    ```

3. Load Data

    Use pgAdmin Import/Export data option and load data from the attached `./Datasets`.
