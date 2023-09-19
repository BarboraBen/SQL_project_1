### Trigger - After inserting new payment, column paid in booking table is set to true.
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

### Trigger - After adding new booking, column total_amount is automatically calculated.
```
CREATE OR REPLACE FUNCTION AmountAfterInsertBookingFc() RETURNS TRIGGER
AS $$
    BEGIN
        UPDATE booking
        SET total_amount = 
		(NEW.no_adults *
			(SELECT price_adult
			FROM holiday_package
			WHERE h_package_id=NEW.h_package_id))
			+
		(NEW.no_children *
			(SELECT price_child
			FROM holiday_package
			WHERE h_package_id=NEW.h_package_id))
		WHERE booking_id=NEW.booking_id;
        RETURN null;
    END;

CREATE OR REPLACE TRIGGER AmountAfterInsertBooking
    AFTER INSERT
    ON booking
    FOR EACH ROW
    EXECUTE FUNCTION AmountAfterInsertBookingFc();
```
