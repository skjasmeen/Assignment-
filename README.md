<?xml version="1.0" encoding="UTF-8"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" elementFormDefault="qualified">
  <!-- Root element that you will send on JMS -->
  <xs:element name="Order">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="OrderId" type="xs:string"/>
        <xs:element name="CustomerName" type="xs:string"/>
        <xs:element name="OrderDate" type="xs:string"/>
        <xs:element name="Items">
          <xs:complexType>
            <xs:sequence>
              <xs:element name="Item" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element name="LineNo" type="xs:int"/>
                    <xs:element name="Sku" type="xs:string"/>
                    <xs:element name="Qty" type="xs:int"/>
                    <xs:element name="Price" type="xs:decimal"/>
                  </xs:sequence>
                </xs:complexType>
              </xs:element>
            </xs:sequence>
          </xs:complexType>
        </xs:element>
        <xs:element name="Totals" minOccurs="0">
          <xs:complexType>
            <xs:sequence>
              <xs:element name="Amount" type="xs:decimal"/>
            </xs:sequence>
          </xs:complexType>
        </xs:element>
      </xs:sequence>
    </xs:complexType>
  </xs:element>
</xs:schema>
