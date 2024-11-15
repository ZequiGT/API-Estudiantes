﻿# API-Estudiantes

# Estructura
API-Estudiantes/
├── cypress/
│   ├── integration/
│   │   ├── registro_spec.js
│   │   ├── consulta_spec.js
│   │   ├── modificacion_spec.js
│   │   └── eliminar_spec.js
│   └── (otros archivos generados por Cypress)
├── cypress.json
└── README.md

## Ejecución de Pruebas Automatizadas con Cypress

### Requisitos Previos
- Node.js y npm instalados

### Instrucciones de Ejecución
1. Clonar el repositorio y navegar a la carpeta raíz.
2. Instalar las dependencias:
   ```bash
   npm install

    npx cypress open

    npx cypress run

###### Pruebas en Cypress
describe('Registro de Estudiantes', () => {
  it('Debería registrar un estudiante con datos válidos', () => {
    cy.visit('/registro'); // Reemplaza con la URL de tu formulario de registro
    cy.get('input[name="nombre"]').type('Juan Perez');
    cy.get('input[name="email"]').type('juan.perez@example.com');
    cy.get('input[name="password"]').type('Password123');
    cy.get('button[type="submit"]').click();
    cy.contains('Registro exitoso').should('be.visible');
  });

  it('Debería mostrar error si el email está vacío', () => {
    cy.visit('/registro');
    cy.get('input[name="nombre"]').type('Maria Lopez');
    cy.get('input[name="password"]').type('Password123');
    cy.get('button[type="submit"]').click();
    cy.contains('El email es obligatorio').should('be.visible');
  });
});


 ### Lista de Estudiantes

 describe('Consulta de Estudiantes', () => {
  it('Debería mostrar la lista de estudiantes registrados', () => {
    cy.visit('/estudiantes'); // Reemplaza con la URL de la lista de estudiantes
    cy.get('table').should('be.visible'); // Verifica que la tabla sea visible
    cy.get('table').find('tr').its('length').should('be.gt', 1); // Verifica que haya al menos un estudiante
  });
});


##### Información de Estudiantes
describe('Modificación de Información de Estudiantes', () => {
  it('Debería modificar el nombre de un estudiante existente', () => {
    cy.visit('/estudiantes'); // URL de la lista de estudiantes
    cy.get('button.edit').first().click(); // Botón para editar el primer estudiante
    cy.get('input[name="nombre"]').clear().type('Juan Carlos Perez');
    cy.get('button[type="submit"]').click();
    cy.contains('Modificación exitosa').should('be.visible');
  });
});


## Eliminación de Estudiantes
describe('Eliminación de Estudiantes', () => {
  it('Debería eliminar un estudiante', () => {
    cy.visit('/estudiantes'); // URL de la lista de estudiantes
    cy.get('button.delete').first().click(); // Botón para eliminar el primer estudiante
    cy.contains('Confirmar eliminación').click(); // Confirmación de eliminación
    cy.contains('Estudiante eliminado').should('be.visible');
  });
});


## Pruebas en Cypress

    npx cypress open


    npx cypress run


## Ejecución de Pruebas Automatizadas con Cypress

### Requisitos Previos
- Node.js y npm instalados

### Instrucciones de Ejecución
1. Clonar el repositorio y navegar a la carpeta raíz.
2. Instalar las dependencias:
   ```bash
   npm install

    npx cypress open

    npx cypress run

