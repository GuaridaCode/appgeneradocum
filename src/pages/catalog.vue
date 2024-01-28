<template>
  <f7-page name="catalog">
    <f7-navbar title="Catalogo"></f7-navbar>
    <f7-list strong dividers-ios outline-ios inset-md>
      <f7-list-item
        v-for="product in products"
        :key="product.id"
        :title="product.title"
        :link="`/product/${product.id}/`"
      >
    <f7-button fill @click="generatePDF">Generar</f7-button>
    </f7-list-item>
      
    </f7-list>
    <f7-block v-if="products.length === 3">
      <f7-button fill @click="addProduct">Agregar Categoria</f7-button>
    </f7-block>
  </f7-page>
</template>
<script>
import { useStore } from 'framework7-vue';
import store from '../js/store';
import html2pdf  from 'html2pdf.js';
import axios from 'axios';

export default {
  setup() {
    const products = useStore('products');

    const addProduct = () => {
      store.dispatch('addProduct', {
        id: '4',
        title: 'Apple iPhone 12',
        description:
          'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nisi tempora similique reiciendis, error nesciunt vero, blanditiis pariatur dolor, minima sed sapiente rerum, dolorem corrupti hic modi praesentium unde saepe perspiciatis.',
      });
    };

    return {
      products,
      addProduct,
    };
  },
  methods: {
    async generatePDF(){
      try{
      const response1= `
      <html>
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>Document</title>
        <style>
            body {
                font-family: Arial, sans-serif;
            }
            .letter {
                max-width: 600px;
                margin: 20px auto;
                padding: 20px;
                border: 1px solid #ccc;
                border-radius: 5px;
            }
        </style>
</head>
<body>
  <div class="letter" id="document">
    <p><strong>[Nombre del Remitente]</strong><br>
    [Dirección del Remitente]<br>
    [Teléfono del Remitente]<br>
    [Correo Electrónico del Remitente]</p>

    <p>[Fecha]</p>

    <p><strong>[Nombre del Destinatario]</strong><br>
    [Título del Destinatario (si es aplicable)]<br>
    [Dirección del Destinatario]</p>

    <p>Estimado/a <strong>[Nombre del Destinatario]</strong>:</p>

    <p>Espero que esta carta le encuentre bien. Me dirijo a usted para solicitar [explique brevemente la solicitud].</p>

    <p>[Proporcione detalles adicionales sobre la solicitud, incluyendo cualquier información relevante que respalde su pedido].</p>

    <p>Me gustaría [mencionar cualquier fecha límite o requisito específico, si es aplicable].</p>

    <p>Agradezco de antemano su atención a esta solicitud y estaré encantado/a de proporcionar cualquier información adicional que pueda ser necesaria.</p>

    <p>Quedo a la espera de su respuesta positiva y agradezco la oportunidad de resolver este asunto.</p>

    <p>Atentamente,</p>

    <p><strong>[Nombre del Remitente]</strong><br>
    [Título del Remitente (si es aplicable)]</p>
    


</div>
  </body>
</html>
      `;
      const contenidoHTML = response1;
      


      // Agrega los datos dinámicos al HTML
      const datosDinamicos = {
        nombreRemitente: 'John Doe',
        direccionRemitente: '123 Main Street',
        telefonoRemitente: '555-1234',
        correoRemitente: 'john@example.com',
        // Agrega más datos según sea necesario
      };


      // Configura las opciones para la generación del PDF
      const opcionesPDF = {
        margin: 10,
        filename: 'documento.pdf',
        image: { type: 'jpeg', quality: 0.98 },
        html2canvas: { scale: 2 },
        jsPDF: { unit: 'mm', format: 'a4', orientation: 'portrait' },
      };

        html2pdf().set(opcionesPDF).from(contenidoHTML).save();
        console.log('PDF Generado!');

      }catch(error){
        console.log('ERROR al generar archivo PDF. ->  ' + error);
      }
    }
  }
};
</script>
