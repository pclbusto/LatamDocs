#LATAM Voucher Class Lookup

##Descripción:
Esta query es un join entre clase de comprobante, tipo clase de comprobante y la lista de voucher que tienen acceso los grupo tipo cuenta. La idea de esta query es aplanar la relaciones que existen entre estas entiedades para poder resolver el lookup de clase comprobante. Clase de comprobante y tipo clase de comprobante se unen por el id de clase de comprobante. con esto se tiene el tipo de clase de comprobante para cada comprobante. Con esto no solo tenemos el tipo de clase de comprobante sino tambien cada flag que indica si es una factura de compras, factura de ventas, remito de ventas, etc. Por ultimo al hacer el join con las clases de comprobante de cada entidad configurada grupo tipo cuenta. obtenemos el id del grupo para poder filtrar con la entidad que corresponda en cada documentos.


