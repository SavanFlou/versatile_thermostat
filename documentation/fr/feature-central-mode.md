
# La configuration centrale

- [La configuration centrale](#La-configuration-centrale)
  - [Configuration](#configuration)
  - [Usage](#usage)

Cette fonction vous permet de contrôler tous vos VTherm depuis un unique point de contrôle.
Le cas d'usage typique est lorsque vous partez pour une longue durée, vous voulez mettre tous vos _VTherm_ en Hors-gel et lorsque vous rentrez, vous voulez les remettre dans l'état initial.

La configuration centrale se fait depuis un Vtherm spécial nommé configuration centrale. Cf. [ici](creation.md#configuration-centralisée) pour plus d'informations.

## Configuration

Si vous avez défini une configuration centralisée, vous avez une nouvelle entité nommée `select.central_mode` qui permet de piloter tous les VTherms avec une seule action.

![central_mode](images/central-mode.png)

Cette entité se présente sous la forme d'une liste de choix qui contient les choix suivants :
1. `Auto` : le mode 'normal' dans lequel chaque VTherm se comporte de façon autonome,
2. `Stopped` : tous les VTherms sont mis à l'arrêt (`hvac_off`),
3. `Heat only` : tous les VTherms sont mis en mode chauffage lorsque ce mode est supporté par le VTherm, sinon il est stoppé,
4. `Cool only` : tous les VTherms sont mis en mode climatisation lorsque ce mode est supporté par le VTherm, sinon il est stoppé,
5. `Frost protection` : tous les VTherms sont mis en preset hors-gel lorsque ce preset est supporté par le VTherm, sinon il est stoppé.

## Usage

Pour qu'un VTherm soit contrôlable de façon centralisée, il faut que son attribut de configuration nommé `use_central_mode` soit vrai. Cet attribut est disponible dans le menu de configuration `Principaux attributs`

![central_mode](images/use-central-mode.png)

Il est donc possible de contrôler tous les VTherms (ou du moins tous ceux que l'on désigne explicitement comme tel) avec un seul contrôle.
