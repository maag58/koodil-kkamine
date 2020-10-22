Pit2gis uue autentija paigaldusjuhend

1. Tomcat seisma

2. Panna autentija koos abiteekidega Tomcat lib kataloogi

AuthTara.jar 
commons-lang-2.6.jar
org.json-chargebee-1.0.jar

3. Seadistada Pit2gis stardikas Pit2gis.xml

Eemaldada eelmise autentija seadistused
<!--
	<Valve className="ee.rsystems.pit.AuthenticatorTara" />
	
	<Parameter name="digidoc-service-url" value="https://tsp.demo.sk.ee/" override="false"/>
	<Parameter name="digidoc-service" value="Testimine" override="false"/>

	<Parameter name="certificates" value="" override="false"/>
	<Parameter name="certificates_psw" value="" override="false"/>
-->

Panna uus seadistus

	<Valve className="ee.rsystems.pit.AuthenticatorTara" />
	
	<Parameter name="TaraAuthorize" value="https://tara-test.ria.ee/oidc/authorize" override="false"/>
	<Parameter name="TaraToken" value="https://tara-test.ria.ee/oidc/token" override="false"/>
	<Parameter name="TaraPublicKey" value="https://tara-test.ria.ee/oidc/jwks" override="false"/>
	<Parameter name="TaraIssuer" value="https://tara-test.ria.ee" override="false"/>
	<Parameter name="TaraClientId" value="PIT2GIS" override="false"/>
	<Parameter name="TaraClientSecret" value="" override="false"/>
	<Parameter name="TaraScope" value="openid" override="false"/>

Siin on vaja õigeks panna TaraClientId kui ka TaraClientSecret

Kui on vajadus piirata autentimisvõimalusi, siis muuta 	parameetrit TaraScope vastavalt RIA juhendile

https://e-gov.github.io/TARA-Doku/TehnilineKirjeldus#41-autentimisp%C3%A4ring ja siit scope.

4.Panna Tomcat käima