# deployment-groupname

Repositorio que contiene los pipelines que orquestan el despliegue.

## ap-groupname-deploy.yml

Pipeline que orquesta el despliegue singlebar o multibar y sus dependencias (policy y/o lib).

Se debe actualizar las siguientes variables definidas con el siguiente formato `<variable>`:
| Variable  | Descripción |
| ------------- | ------------- |
| endpoint | Endpoint de conexión al repositorio GIT. |
| organizacion | Nombre de la organizacion asociada al repositorio GIT. |
| repositorio | Nombre del repositorio GIT.  |
| poolname | Nombre del agente.  |
| policyname | Nombre de la politica de ACE.  |
| apiname | Nombre de la aplicación de ACE.  |
| libname | Nombre del shared library de ACE.  |

## variables.yml

Archivo que contiene todos los variable groups por ambiente requeridos en los procesos de deploy y publish. Estos deberán crearse por cada ambiente a desplegar.

Los group names definidos son los siguientes:

### gitops-cred-sb-001

| Nombre  | Descripción |
| ------------- | ------------- |
| argoPass | Contraseña de conexión a Openshift Git Ops. |
| argoUser | Nombre de usuario de conexión a Openshift Git Ops. |
| argoServer | Hostname de conexión a Openshift Git Ops. |

### gitops-app-sb-001

| Nombre  | Descripción |
| ------------- | ------------- |
| argoApp | Nombre de la aplicación de Openshift Git Ops asociada al proyecto integration-server. |
| barURL | URL o URLs de los artefactos BAR. |

### env-sb-001

| Nombre  | Descripción |
| ------------- | ------------- |
| namespaceSecret | Namespace donde se desplegaran los componentes. |

### cluster-env-dev-001

| Nombre  | Descripción |
| ------------- | ------------- |
| environmentValue | Nombre del ambiente (Ejemplo: sandbox) |
| kubernetesEndpoint | Nombre del service connection de Openshift. |
| serverURLJFrog | Hostname de conexión a JFrog. |
