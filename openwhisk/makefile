.PHONY: clean realclean build test bluemix

all: clean build

VERSION=$(shell cat VERSION)

clean:
	-@rm -f *.zip
	-@rm -f __main__.py

build:
	@cp insert.py __main__.py
	zip -r insert-$(VERSION).zip __main__.py db2.py
	@cp ts.py __main__.py
	zip -r get_ts-$(VERSION).zip __main__.py db2.py
	@cp devices.py __main__.py
	zip -r get_devices-$(VERSION).zip __main__.py db2.py

bluemix:
	bx wsk action invoke Cristata-TimeSeriesRetrieve -P request.json --result
	bx wsk action invoke Cristata-DeviceListing --result

