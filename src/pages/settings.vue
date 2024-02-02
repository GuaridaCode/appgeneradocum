<template>
  <f7-page name="settings">
    <f7-navbar title="Ajustes"></f7-navbar>

    <f7-block-title>Datos de Usuario</f7-block-title>
    <f7-list strong-ios dividers-ios outline-ios>
      <f7-list-input label="Nombre Completo" type="text" placeholder="Paterno Materno Nombres"></f7-list-input>

      <f7-list-input label="Correo" type="email" placeholder="ejemplo@gmail.com"></f7-list-input>

      <f7-list-input label="Documento de Identidad" type="url" placeholder="#######"></f7-list-input>

      <f7-list-input label="Telefono" type="password" placeholder="400-0000"></f7-list-input>

      <f7-list-input label="Celular" type="tel" placeholder="+5199999999"></f7-list-input>

<!--       <f7-list-input label="Sexo" type="select">
        <option>Male</option>
        <option>Female</option>
      </f7-list-input> -->

      <f7-list-input
        label="Nacimiento"
        type="date"
        placeholder="Birth day"
        defaultValue="2014-04-30"
      ></f7-list-input>

      <f7-list-item title="Firma">
        <template #after>
          <f7-toggle />
        </template>
      </f7-list-item>

<!--       <f7-list-input label="Range" :input="false">
        <template #input>
          <f7-range :value="50" :min="0" :max="100" :step="1" />
        </template>
      </f7-list-input> -->

      <f7-list-input type="textarea" label="Quien eres?" placeholder="Describe algo breve de ti"></f7-list-input>
      <f7-list-input type="textarea" label="A que te dedicas?" placeholder="Ejemplo: soy carpintero" resizable></f7-list-input>
    </f7-list>

<!--     <f7-block-title>Buttons</f7-block-title>
    <f7-block strong-ios outline-ios class="grid grid-cols-2 grid-gap">
      <f7-button>Button</f7-button>
      <f7-button fill>Fill</f7-button>

      <f7-button raised>Raised</f7-button>
      <f7-button raised fill>Raised Fill</f7-button>

      <f7-button round>Round</f7-button>
      <f7-button round fill>Round Fill</f7-button>

      <f7-button outline>Outline</f7-button>
      <f7-button round outline>Outline Round</f7-button>

      <f7-button small outline>Small</f7-button>
      <f7-button small round outline>Small Round</f7-button>

      <f7-button small fill>Small</f7-button>
      <f7-button small round fill>Small Round</f7-button>

      <f7-button large raised>Large</f7-button>
      <f7-button large fill raised>Large Fill</f7-button>

      <f7-button large fill raised color="red">Large Red</f7-button>
      <f7-button large fill raised color="green">Large Green</f7-button>
    </f7-block> -->

    <f7-block-title>Cuentanos tus intereses</f7-block-title>
    <f7-list strong-ios outline-ios dividers-ios>
      <f7-list-item checkbox name="my-checkbox" value="Books" title="Carta"></f7-list-item>
      <f7-list-item checkbox name="my-checkbox" value="Movies" title="Solicitud"></f7-list-item>
      <f7-list-item checkbox name="my-checkbox" value="Food" title="Informe"></f7-list-item>
      <f7-list-item checkbox name="my-checkbox" value="Food" title="Constancia"></f7-list-item>
      <f7-list-item checkbox name="my-checkbox" value="Food" title="Licencia"></f7-list-item>
      <f7-list-item checkbox name="my-checkbox" value="Food" title="Seguro"></f7-list-item>
      <f7-list-item checkbox name="my-checkbox" value="Food" title="Comunicado"></f7-list-item>

      <f7-list-input type="textarea" label="Que sugieres?" placeholder="escribe tu idea" resizable></f7-list-input>
    </f7-list>

    <f7-block-title>Que opinas?</f7-block-title>
    <p style="padding-left:18px;">Es importante para mejorar que nos cuentes mediante esta eleccion.</p>
    <f7-list strong-ios outline-ios dividers-ios>
      <f7-list-item radio name="radio" value="Books" title="muy util"></f7-list-item>
      <f7-list-item radio name="radio" value="Movies" title="no lo se"></f7-list-item>
      <f7-list-item radio name="radio" value="Food" title="no me sirvió"></f7-list-item>

      <f7-block strong-ios outline-ios class="grid grid-cols-0 grid-gap">
        <f7-button outline>Enviar mi opinion</f7-button>
      </f7-block>
    </f7-list>

    
    <br>

  </f7-page>
</template>
