### Trigger - After inserting new payment column paid in booking table is set to true.
```
CREATE OR REPLACE FUNCTION AfterInsertPaymentFc() RETURNS TRIGGER
AS $$
    BEGIN
        UPDATE booking
        SET paid = 'True'
		    WHERE booking_id=NEW.booking_id;
        RETURN null;
    END;
$$ LANGUAGE plpgsql;

CREATE OR REPLACE TRIGGER AfterInsertPayment
    AFTER INSERT
    ON payment
    FOR EACH ROW
    EXECUTE FUNCTION AfterInsertPaymentFc();
```
