# Comment utilisez-vous les mixins en CLI ?

Relue ?: No

À l'aide de Vue CLI, les mixins peuvent être spécifiés n'importe où dans le dossier du projet, mais de préférence dans `/src/mixins`pour faciliter l'accès.  Une fois ces mixins créés dans un `.js`fichier et exposé avec le `export`mot-clé, ils peuvent être importés dans n'importe quel composant avec le `import`mot-clé et leurs chemins de fichiers.