---
title: Asignar restricciones KEY de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: 46a980f06198c6f06bb13824c65cfb5309eec154
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034234"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a>Asignar restricciones KEY de un esquema XML (XSD) a restricciones de conjuntos de datos
En un esquema, puede especificar una restricción de clave en un elemento o atributo con el **clave** elemento. El elemento o el atributo para el que se especifica una restricción de clave debe tener valores únicos en cualquier instancia del esquema y no puede tener valores nulos.  
  
 La restricción de clave es similar a la restricción única, excepto en que la columna sobre la que se define una restricción de clave no puede tener valores nulos.  
  
 La siguiente tabla se describen los **msdata** atributos que se pueden especificar en el **clave** elemento.  
  
|Nombre del atributo|Descripción|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|Si se especifica este atributo, su valor se utiliza como nombre de la restricción. En caso contrario, el **nombre** atributo proporciona el valor del nombre de restricción.|  
|**msdata:PrimaryKey**|Si `PrimaryKey="true"` está presente, el **IsPrimaryKey** propiedad de restricción se establece en **true**, lo que una clave principal. El **AllowDBNull** propiedad de columna se establece en **false**, porque las claves principales no pueden tener valores null.|  
  
 Convertir un esquema en el que se especifica una restricción de clave, el proceso de asignación crea una restricción unique en la tabla con el **AllowDBNull** propiedad column definida en **false** para cada columna en el restricción. El **IsPrimaryKey** también se establece la propiedad de la restricción unique en **false** a menos que haya especificado `msdata:PrimaryKey="true"` en el **clave** elemento. Esto es idéntico a una restricción única del esquema donde `PrimaryKey="true"`.  
  
 En el siguiente ejemplo de esquema, el **clave** elemento especifica la restricción de clave en el **CustomerID** elemento.  
  
```xml  
<xs:schema id="cod"  
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
        <xs:element name="CompanyName" type="xs:string" minOccurs="0" />  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
<xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:key  msdata:PrimaryKey="true"  
       msdata:ConstraintName="KeyCustID"  
          name="KeyConstCustomerID" >  
     <xs:selector xpath=".//Customers" />  
     <xs:field xpath="CustomerID" />  
    </xs:key>  
 </xs:element>  
</xs:schema>   
```  
  
 El **clave** elemento especifica que los valores de la **CustomerID** elemento secundario de la **clientes** elemento debe tener valores únicos y no pueden tener valores null. Al traducir el esquema del lenguaje de definición de esquema XML (XSD), el proceso de asignación crea la tabla siguiente:  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 La asignación de esquema XML crea también un **UniqueConstraint** en el **CustomerID** columna, como se muestra en la siguiente <xref:System.Data.DataSet>. Para simplificar, sólo se muestran las propiedades relevantes.  
  
```  
      DataSetName: MyDataSet  
TableName: customers  
  ColumnName: CustomerID  
      AllowDBNull: False  
      Unique: True  
  ConstraintName: KeyCustID  
      Table: customers  
      Columns: CustomerID   
      IsPrimaryKey: True  
```  
  
 En el **DataSet** que se genera, la **IsPrimaryKey** propiedad de la **UniqueConstraint** está establecido en **true** porque el esquema especifica `msdata:PrimaryKey="true"` en el **clave** elemento.  
  
 El valor de la **ConstraintName** propiedad de la **UniqueConstraint** en el **DataSet** es el valor de la **msdata: ConstraintName** atributo especificado en el **clave** elemento del esquema.  
  
## <a name="see-also"></a>Vea también

- [Asignación de restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Generación de relaciones de objetos DataSet en un esquema XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
