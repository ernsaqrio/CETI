mindmap
  root((PKI\nIndustrias MarMon))
    CA Raíz
      Par de claves
        Clave privada
        Clave pública
      Certificado raíz
        Autofirmado
        X.509
      Base de datos
        index.txt
        serial
        crlnumber

    Solicitud de Certificado (CSR)
      Formato PKCS#10
      Contiene
        Clave pública
        Identidad del sujeto
      Pendiente de firma
        CA emisora

    Emisión de Certificado
      Firma de la CA
      Certificado X.509
      Almacenamiento
        certs/
        newcerts/
      Registro
        index.txt

    Uso del Certificado
      Autenticación
      Firma digital
      Cifrado
      Exportación
        PKCS#12 (.p12)
        Navegadores
        Clientes de correo

    Revocación
      Motivos
        Compromiso de clave
        Fin de validez
        Cambio de identidad
      Registro en CA
        index.txt

    CRL
      Lista de revocación
      Firmada por la CA
      Publicación periódica
      Ubicación
        crl/ca.crl.pem

    OCSP
      Validación en tiempo real
      Servidor OCSP
      Estados
        good
        revoked
        unknown
      Referenciado en certificados
