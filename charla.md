# Como viajar en el tiempo con mucho menos que un Delorean

## El problema (Por qué necesitamos con SCV)

 * Se me rompe el disco y pierdo todo mi trabajo
 
 * Estuve toda la noche haciendo cambios, quedó peor, la version anterior
   era mejor
 
 * Cambios en producción mientras seguimos trabajando en la próxima versión
 
 * proyecto_2013_02_04 
 
 * proyecto_2013_02_04_version_definitiva
 
 * proyecto_2013_02_04_version_definitiva_esta_si
 
 * proyecto_2013_02_04_version_definitiva_esta_si_ok_correjida 

 * Varias personas trabajando en el mismo proyecto
 
## Ventajas de usar un sistema de control de versiones

 * Le da al equipo un botón de **Deshacer**, imaginen usar
   un procesador de texto que no tenga el botón borrar, 
   nos haría demasiado lentos.
   
 * Permiten que varias personas trabajen en el mismo proyecto, modificando
   los mismos archivos, en el mismo momento, desde distintos puntos
   geográficos.
 
 * El sistema de control de versiones lleva un registros de todos los cambios
   hechos en el tiempo, si nos encontramos con algo raro, es fácil
   quién hizo ese cambio y cuando.
 
 * Permite trabajar con varios "releases" de tu software y al mismo tiempo
   tiempo continuar con la rama principal del trabajo.
 
 * Un sistema de control de versiones es una máquina del tiempo por que te permite ir a uan fecha específica y ver como era exactamente el proyecto en ese momento.

## Sitema de control de versiones centralizado

  * Cvs, Svn, Perforce
  
  * Un solo servidor que guarda todos los archivos versionados, y varios
    clientes que extraen los archivos desde este lugar central.
	
	--Acá va la imágen centralized-scv.png--

  Los scv centralizados tiene varias ventajas por sobre el sistema "a mano",
  
  * Todos tiene alguna idea acerca de en qué está trabajando cada uno
  
  * Los administradores tiene un control sobre quién puede hacer qué.
  
  
  Sin embargo este este sistema tiene serios problemas:
  
  * Un único punto de fallo que los servers centralizados representan.
  
    * Si el server se cae durante 2hs nadie puede colaborar durante
	  ese período.
	  
	* Sí el disco del servidor se rompe, y no se hizo un backup, perdemos
	  absolutamente todo.

## Sistemas de control de Versiones distribuidos

   * Git, Mercurial, Bazaar, Darcs
   
   * No sólo tienen un snapshot de los archivos sino que tiene
     una copia del repositorio completa.
	 
   * Si algún servidor se muere cualquier cliente que haya estado
     colaborando hacia este puede ser copiado y usado como backup.
	 
   * Cada checkout es realmente una completo backup.	 

   	--Acá va la imágen distributed-scv.png--
	
## La historia de Git

  * Como muchas de las grandes cosas de esta vida, git comenzó con un poco
  de destrucción creativa y polémica. 

  * Entre 1991-2002 los cambios en el kernel de linux se pasaban en forma de parches y archivos.
  
  * En el 2002 comezó a usar un scvd propietario llamado BitKeeper
  
  * En el 2005 la relación entre la companía que desarrollaba BitKeeper y la comunidad de Linux se vino abajo.
 
  * Esto impulsó a la comunindad y a Linus en particular a desarrollar su propia herramienta, basándose en algunas lecciones aprendidas de BitKeeper:
  
    * Velocidad
	* Diseño sencillo
	* Fuerte apoyo en el desarrollo no lineal
	* Completamente distribuido
	* Capáz de manejar proyectos grandes como el Kernel Linux
  
## Fundamentos de Git

   * Instantáneas, no diferencias
   
   * Conceptualmente, la mayoría de los demás sistemas almacenan la información como una lista de cambios en los archivos. 
   
   -- Acá va la imágen: diferencias-entre-archivos.png --
   
   * Git no modela ni almacena sus datos de este modo. En cambio, Git modela sus datos más como un conjunto de instantáneas de un mini sistema de archivos. 
   
   -- Acá va la imágen: instantaneas.png --
   
## Ventajas de trabajar con instantáneas

   * Casi cualquier operación es local, no necesitamos de la red.
     Esto hace que por ej, si te subís a un avión y querés seguir
	 trabajando lo podés hacer.
	 
## Git tiene integridad

   * Todo en git es verificado mediante un checksum.
   
   * El mecanismo que git usa para esto es una hash SHA-1 (40 chars en hexa)
     
	 24b9da6552252987aa493b52f8696cd6d3b00373

   * Git guarda todo no por nombres de archivos sino por el valor hash de su contenido
   
   
## Git solo agrega información

   * Es muy difícil conseguir que el sistema haga algo que no se pueda deshacer
   
   * Esto hace que usar Git sea un placer, porque sabemos que podemos experimentar sin peligro de fastidiar gravemente las cosas
   
## Instalando git

## Configurando git
   
## Fuentes: 

 * Pragmatic Version control with subversion.
 * http://git-scm.com/book
