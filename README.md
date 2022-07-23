# DataHarmonizer

A standardized spreadsheet editor and validator that can be run offline and locally, and which includes templates for SARS-CoV-2 sampling data.  

Watch Rhiannon Cameron and Damion Dooley describe this application on [YouTube](https://www.youtube.com/watch?v=rdN2_Vhwb8E&t=38s&ab_channel=CANARIEInc.) at the Canadian Research Software Conference (CRSC2021).

|Chrome|Firefox|Edge|
|---|---|---|
|49+|34+|12+|

![alt text](./images/editCopyPasteDelete.gif)

## Installation

Download the zipped source code from the latest release at:
https://github.com/Public-Health-Bioinformatics/DataHarmonizer/releases

Extract the zipped file.

To run the application, navigate to the extracted folder and open `index.html`.

## Select Template

The default template loaded is the "CanCOGeN Covid-19" template. To change the spreadsheet template, select the white text box to the right of **Template**, it always contains the name of template currently active, or navigated to **File** followed by **Change Template**. An in-app window will appear that allows you to select from the available templates in the drop-down menu. After selecting the desired template, click **Open** to activate the template.

![change template](./images/changeTemplate.gif)

A second way to access templates directly, rather than by the hard-coded menu system, is to specify the DataHarmonizer template subfolder via a "template" URL parameter. This enables development and use of customized templates, or new ones, that DH doesn't have programmed in menu.  

For example,
http://genepio.org/DataHarmonizer/main.html?template=gisaid accesses the /template/gsiaid/ subfolder's template directly.  

See more on the Wiki [DataHarmonizer templates](https://github.com/Public-Health-Bioinformatics/DataHarmonizer/wiki/DataHarmonizer-Templates) page.

## Usage

You can edit the cells manually, or upload `xlsx`, `xls`, `tsv` and `csv` files via **File** > **Open**. You can also save the spreadsheet's contents to your local hard-drive in the aforementioned formats, or **File** > **Export** your data as an `.xls` document formatted for submission a specified portal, database, or repository.

![saving and exporting files](./images/exportingFiles.gif)

Click the **Validate** button to validate your spreadsheet's values against a
standardized vocabulary. You can then browse through the errors using the **Next Error** button. Missing value are indicated in _dark red_, while incorrect values are _light red_.

![validating cells and checking next error](./images/validatingCells.gif)

Double click any column headers for information on the template's vocabulary.

![double click headers for more info](./images/doubleClickHeaders.gif)

You can quickly navigate to a column by selecting **Settings** > **Jump to...**. An in-app window will appear, select the desired column header from the drop-down list or begin typing it's name to narrow down the list options. Selecting the column header from the drop down list will immediately relocate you to that column on the spreadsheet.

![jump to column](./images/jumpToColumn.gif)

You can also automatically fill a column with a specified value, but only in rows with corresponding values in the first `sample ID` column. To use this feature select **Settings** > **Fill column...**. Select the desired column header from the drop-down list or begin typing it's name to narrow down the list options, then specify the value to fill with and click **Ok** to apply.

![fill column, in rows with corresponding sample IDs, with specified value](./images/fillColumn.gif)

For _more information_ on available application features, select the **Help** button followed by **Getting Started** from within the DataHarmonizer application.

## Example Data

Templates with example data testing functionalities can be found within the following folder structure when available:

```
. TOP LEVEL DIRECTORY
├── images
├── libraries
├── script
└── template
│   ├── templateOfInterest
│   │   └── exampleInput
│   └── ...
```

Alternatively, you can find links to all available test data below:
- [`canada_covid19`](https://github.com/cidgoh/DataHarmonizer/tree/master/template/canada_covid19/exampleInput) CanCOGeN Covid-19

## Additional Information

For more information about the DataHarmonizer, it's templates, and how to use them, check out the [DataHarmonizer Wiki](https://github.com/Public-Health-Bioinformatics/DataHarmonizer/wiki).

## Support

If you have any ideas for improving the application, or have encountered any
problems running the application, [please open an issue for discussion][1].

[1]: https://github.com/Public-Health-Bioinformatics/DataHarmonizer/issues

## Roadmap

This project is currently in the beta phase, with new features being added
occasionally.

## Version Control

Versioning of templates, features, and functionality is modeled on semantic versioning (i.e. versions are expressed as “DataHarmonizer X.Y.Z”).
Changes to vocabulary in template pick lists are updated by incremental increases to the third position in the version (i.e. “Z” position).
Changes to fields and features are updated by incremental increases to the second position in the version (i.e. “Y” position).
Changes to basic infrastructure or major changes to functionality are updated by incremental increases to the first position in the version (i.e. “X” position).

Descriptions of updates are provided in release notes for every new version.

Discussions contributing to updates may be tracked on the DataHarmonizer GitHub Issuetracker.

## Development

Code in this repository is split mainly between two folders: `lib` and `web`. The `lib` folder contains the core interface components which are published to NPM and can be used by any client to build a user interface. The `web` folder contains an implementation of one such interface, using the components defined in `lib`. The interface implemented in the `web` folder is packaged and [made available to users as releases of this repository](#Installation).

### Prerequisites

For development, you must have [Node.js](https://nodejs.org) and [Yarn](https://yarnpkg.com/getting-started/install) installed. If you have Node.js version 16.10 or later (highly recommended) and you have not used Yarn before, you can enable it by running:

```shell
corepack enable
```

### Installing

To install the dependencies of this package for development simply run:

```shell
yarn
```

### Running Locally

Developing either the library components in `lib` or the interface in `web` can be done using the same command:

```shell
yarn dev
```

This will start a [webpack development server](https://webpack.js.org/configuration/dev-server/) running locally on `localhost:8080`. Changes to either `lib` or `web` should be loaded automatically in your browser. This serves as interface for testing and debugging the core library components (in the lib directory) and that interface itself (the web directory).

### Publishing and Releasing

To bundle the canonical interface run:

```shell
yarn build:web
```
You can open web/dist/index.html in your browser to test the distributable bundle and verify it runs in "offline".

To bundle the library components into lib/dist for downstream clients to use via API instead of the canonical interface, run:

```shell
Run yarn build:lib
```

`TODO: describe how to prepare a release containing just the web/dist/ folder and templates; and describe how to use the API.`

## Acknowledgement

- [Handsontable](https://handsontable.com/) was used to build the grid.  DataHarmonizer is configured to reference the "non-commercial-and-evaluation" handsontable license "for purposes not intended toward monetary compensation such as, but not limited to, teaching, academic research, evaluation, testing and experimentation"; if this application is used for commercial purposes, this should be revised as per https://handsontable.com/docs/license-key/
- [SheetJS](https://sheetjs.com/) was used to open and save local files. The community edition was used under the [Apache 2.0](https://github.com/SheetJS/sheetjs/blob/master/LICENSE) license.

## License

DataHarmonizer javascript, python and other code not mentioned in the Acknowledgement above is covered by the [MIT](LICENSE) license.

