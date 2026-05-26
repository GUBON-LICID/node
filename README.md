# Node.js

Node.js is an open-source, cross-platform JavaScript runtime environment.

For information on using Node.js, see the [Node.js website][].

The Node.js project uses an [open governance model](./GOVERNANCE.md). The
[OpenJS Foundation][] provides support for the project.

Contributors are expected to act in a collaborative manner to move
the project forward. We encourage the constructive exchange of contrary
opinions and compromise. The [TSC](./GOVERNANCE.md#technical-steering-committee)
reserves the right to limit or block contributors who repeatedly act in ways
that discourage, exhaust, or otherwise negatively affect other participants.

**This project has a [Code of Conduct][].**

## Table of contents

* [Support](#support)
* [Release types](#release-types)
  * [Download](#download)
    * [Current and LTS releases](#current-and-lts-releases)
    * [Nightly releases](#nightly-releases)
    * [API documentation](#api-documentation)
  * [Verifying binaries](#verifying-binaries)
* [Building Node.js](#building-nodejs)
* [Security](#security)
* [Contributing to Node.js](#contributing-to-nodejs)
* [Current project team members](#current-project-team-members)
  * [TSC (Technical Steering Committee)](#tsc-technical-steering-committee)
  * [Collaborators](#collaborators)
  * [Triagers](#triagers)
  * [Release keys](#release-keys)
* [License](#license)

## Support

Looking for help? Check out the
[instructions for getting support](.github/SUPPORT.md).

## Release types

* **Current**: Under active development. Code for the Current release is in the
  branch for its major version number (for example,
  [v22.x](https://github.com/nodejs/node/tree/v22.x)). Node.js releases a new
  major version every 6 months, allowing for breaking changes. This happens in
  April and October every year. Releases appearing each October have a support
  life of 8 months. Releases appearing each April convert to LTS (see below)
  each October.
* **LTS**: Releases that receive Long Term Support, with a focus on stability
  and security. Every even-numbered major version will become an LTS release.
  LTS releases receive 12 months of _Active LTS_ support and a further 18 months
  of _Maintenance_. LTS release lines have alphabetically-ordered code names,
  beginning with v4 Argon. There are no breaking changes or feature additions,
  except in some special circumstances.
* **Nightly**: Code from the Current branch built every 24-hours when there are
  changes. Use with caution.

Current and LTS releases follow [semantic versioning](https://semver.org). A
member of the Release Team [signs](#release-keys) each Current and LTS release.
For more information, see the
[Release README](https://github.com/nodejs/Release#readme).

### Download

Binaries, installers, and source tarballs are available at
<https://nodejs.org/en/download/>.

#### Current and LTS releases

<https://nodejs.org/download/release/>

The [latest](https://nodejs.org/download/release/latest/) directory is an
alias for the latest Current release. The latest-_codename_ directory is an
alias for the latest release from an LTS line. For example, the
[latest-hydrogen](https://nodejs.org/download/release/latest-hydrogen/)
directory contains the latest Hydrogen (Node.js 18) release.

#### Nightly releases

<https://nodejs.org/download/nightly/>

Each directory and filename includes the version (e.g., `v22.0.0`),
followed by the UTC date (e.g., `20240424` for April 24, 2024),
and the short commit SHA of the HEAD of the release (e.g., `ddd0a9e494`).
For instance, a full directory name might look like `v22.0.0-nightly20240424ddd0a9e494`.

#### API documentation

Documentation for the latest Current release is at <https://nodejs.org/api/>.
Version-specific documentation is available in each release directory in the
_docs_ subdirectory. Version-specific documentation is also at
<https://nodejs.org/download/docs/>.

### Verifying binaries

Download directories contain a `SHASUMS256.txt.asc` file with SHA checksums for the
files and the releaser PGP signature.

You can get a trusted keyring from nodejs/release-keys, e.g. using `curl`:

```bash
curl -fsLo "/path/to/nodejs-keyring.kbx" "https://github.com/nodejs/release-keys/raw/HEAD/gpg/pubring.kbx"
```

Alternatively, you can import the releaser keys in your default keyring, see
[Release keys](#release-keys) for commands on how to do that.

Then, you can verify the files you've downloaded locally
(if you're using your default keyring, pass `--keyring="${GNUPGHOME:-~/.gnupg}/pubring.kbx"`):

```bash
curl -fsO "https://nodejs.org/dist/${VERSION}/SHASUMS256.txt.asc" \
&& gpgv --keyring="/path/to/nodejs-keyring.kbx" --output SHASUMS256.txt < SHASUMS256.txt.asc \
&& shasum --check SHASUMS256.txt --ignore-missing
```

## Building Node.js

See [BUILDING.md](BUILDING.md) for instructions on how to build Node.js from
source and a list of supported platforms.

## Security

For information on reporting security vulnerabilities in Node.js, see
[SECURITY.md](./SECURITY.md).

## Contributing to Node.js

* [Contributing to the project][]
* [Working Groups][]
* [Strategic initiatives][]
* [Technical values and prioritization][]

## Current project team members

For information about the governance of the Node.js project, see
[GOVERNANCE.md](./GOVERNANCE.md).

<!-- node-core-utils and find-inactive-tsc.mjs depend on the format of the TSC
     list. If the format changes, those utilities need to be tested and
     updated. -->

### TSC (Technical Steering Committee)

#### TSC voting members

<!--lint disable prohibited-strings-->

* [aduh95](https://github.com/aduh95) -
  **Antoine du Hamel** <<duhamelantoine1995@gmail.com>> (he/him)
* [anonrig](https://github.com/anonrig) -
  **Yagiz Nizipli** <<yagiz@nizipli.com>> (he/him)
* [benjamingr](https://github.com/benjamingr) -
  **Benjamin Gruenbaum** <<benjamingr@gmail.com>>
* [BridgeAR](https://github.com/BridgeAR) -
  **Ruben Bridgewater** <<ruben@bridgewater.de>> (he/him)
* [gireeshpunathil](https://github.com/gireeshpunathil) -
  **Gireesh Punathil** <<gpunathi@in.ibm.com>> (he/him)
* [jasnell](https://github.com/jasnell) -
  **James M Snell** <<jasnell@gmail.com>> (he/him)
* [joyeecheung](https://github.com/joyeecheung) -
  **Joyee Cheung** <<joyeec9h3@gmail.com>> (she/her)
* [legendecas](https://github.com/legendecas) -
  **Chengzhong Wu** <<legendecas@gmail.com>> (he/him)
* [marco-ippolito](https://github.com/marco-ippolito) -
  **Marco Ippolito** <<marcoippolito54@gmail.com>> (he/him)
* [mcollina](https://github.com/mcollina) -
  **Matteo Collina** <<matteo.collina@gmail.com>> (he/him)
* [panva](https://github.com/panva) -
  **Filip Skokan** <<panva.ip@gmail.com>> (he/him)
* [RafaelGSS](https://github.com/RafaelGSS) -
  **Rafael Gonzaga** <<rafael.nunu@hotmail.com>> (he/him)
* [RaisinTen](https://github.com/RaisinTen) -
  **Darshan Sen** <<raisinten@gmail.com>> (he/him)
* [richardlau](https://github.com/richardlau) -
  **Richard Lau** <<richard.lau@ibm.com>>
* [ronag](https://github.com/ronag) -
  **Robert Nagy** <<ronagy@icloud.com>>
* [ruyadorno](https://github.com/ruyadorno) -
  **Ruy Adorno** <<ruy@vlt.sh>> (he/him)
* [ShogunPanda](https://github.com/ShogunPanda) -
  **Paolo Insogna** <<paolo@cowtech.it>> (he/him)
* [targos](https://github.com/targos) -
  **Michaël Zasso** <<targos@protonmail.com>> (he/him)
* [tniessen](https://github.com/tniessen) -
  **Tobias Nießen** <<tniessen@tnie.de>> (he/him)

#### TSC regular members

* [BethGriggs](https://github.com/BethGriggs) -
  **Beth Griggs** <<bethanyngriggs@gmail.com>> (she/her)
* [bnoordhuis](https://github.com/bnoordhuis) -
  **Ben Noordhuis** <<info@bnoordhuis.nl>>
* [cjihrig](https://github.com/cjihrig) -
  **Colin Ihrig** <<cjihrig@gmail.com>> (he/him)
* [codebytere](https://github.com/codebytere) -
  **Shelley Vohr** <<shelley.vohr@gmail.com>> (she/her)
* [GeoffreyBooth](https://github.com/GeoffreyBooth) -
  **Geoffrey Booth** <<webadmin@geoffreybooth.com>> (he/him)
* [MoLow](https://github.com/MoLow) -
  **Moshe Atlow** <<moshe@atlow.co.il>> (he/him)
* [Trott](https://github.com/Trott) -
  **Rich Trott** <<rtrott@gmail.com>> (he/him)

<details>

<summary>TSC emeriti members</summary>

#### TSC emeriti members

* [addaleax](https://github.com/addaleax) -
  **Anna Henningsen** <<anna@addaleax.net>> (she/her)
* [apapirovski](https://github.com/apapirovski) -
  **Anatoli Papirovski** <<apapirovski@mac.com>> (he/him)
* [ChALkeR](https://github.com/ChALkeR) -
  **Сковорода Никита Андреевич** <<chalkerx@gmail.com>> (he/him)
* [chrisdickinson](https://github.com/chrisdickinson) -
  **Chris Dickinson** <<christopher.s.dickinson@gmail.com>>
* [danbev](https://github.com/danbev) -
  **Daniel Bevenius** <<daniel.bevenius@gmail.com>> (he/him)
* [danielleadams](https://github.com/danielleadams) -
  **Danielle Adams** <<adamzdanielle@gmail.com>> (she/her)
* [evanlucas](https://github.com/evanlucas) -
  **Evan Lucas** <<evanlucas@me.com>> (he/him)
* [fhinkel](https://github.com/fhinkel) -
  **Franziska Hinkelmann** <<franziska.hinkelmann@gmail.com>> (she/her)
* [Fishrock123](https://github.com/Fishrock123) -
  **Jeremiah Senkpiel** <<fishrock123@rocketmail.com>> (he/they)
* [gabrielschulhof](https://github.com/gabrielschulhof) -
  **Gabriel Schulhof** <<gabrielschulhof@gmail.com>>
* [gibfahn](https://github.com/gibfahn) -
  **Gibson Fahnestock** <<gibfahn@gmail.com>> (he/him)
* [indutny](https://github.com/indutny) -
  **Fedor Indutny** <<fedor@indutny.com>>
* [isaacs](https://github.com/isaacs) -
  **Isaac Z. Schlueter** <<i@izs.me>>
* [joshgav](https://github.com/joshgav) -
  **Josh Gavant** <<josh.gavant@outlook.com>>
* [mhdawson](https://github.com/mhdawson) -
  **Michael Dawson** <<midawson@redhat.com>> (he/him)
* [mmarchini](https://github.com/mmarchini) -
  **Mary Marchini** <<oss@mmarchini.me>> (she/her)
* [mscdex](https://github.com/mscdex) -
  **Brian White** <<mscdex@mscdex.net>>
* [MylesBorins](https://github.com/MylesBorins) -
  **Myles Borins** <<myles.borins@gmail.com>> (he/him)
* [nebrius](https://github.com/nebrius) -
  **Bryan Hughes** <<bryan@nebri.us>>
* [ofrobots](https://github.com/ofrobots) -
  **Ali Ijaz Sheikh** <<ofrobots@google.com>> (he/him)
* [orangemocha](https://github.com/orangemocha) -
  **Alexis Campailla** <<orangemocha@nodejs.org>>
* [piscisaureus](https://github.com/piscisaureus) -
  **Bert Belder** <<bertbelder@gmail.com>>
* [rvagg](https://github.com/rvagg) -
  **Rod Vagg** <<r@va.gg>>
* [sam-github](https://github.com/sam-github) -
  **Sam Roberts** <<vieuxtech@gmail.com>>
* [shigeki](https://github.com/shigeki) -
  **Shigeki Ohtsu** <<ohtsu@ohtsu.org>> (he/him)
* [thefourtheye](https://github.com/thefourtheye) -
  **Sakthipriyan Vairamani** <<thechargingvolcano@gmail.com>> (he/him)
* [TimothyGu](https://github.com/TimothyGu) -
  **Tiancheng "Timothy" Gu** <<timothygu99@gmail.com>> (he/him)
* [trevnorris](https://github.com/trevnorris) -
  **Trevor Norris** <<trev.norris@gmail.com>>

</details>

<!-- node-core-utils and find-inactive-collaborators.mjs depend on the format
     of the collaborator list. If the format changes, those utilities need to be
     tested and updated. -->

### Collaborators

* [abmusse](https://github.com/abmusse) -
  **Abdirahim Musse** <<abdirahim.musse@ibm.com>>
* [addaleax](https://github.com/addaleax) -
  **Anna Henningsen** <<anna@addaleax.net>> (she/her)
* [Aditi-1400](https://github.com/Aditi-1400) -
  **Aditi Singh** <<aditisingh1400@gmail.com>> (she/her)
* [aduh95](https://github.com/aduh95) -
  **Antoine du Hamel** <<duhamelantoine1995@gmail.com>> (he/him) - [Support me](https://github.com/sponsors/aduh95)
* [anonrig](https://github.com/anonrig) -
  **Yagiz Nizipli** <<yagiz@nizipli.com>> (he/him) - [Support me](https://github.com/sponsors/anonrig)
* [atlowChemi](https://github.com/atlowChemi) -
  **Chemi Atlow** <<chemi@atlow.co.il>> (he/him)
* [avivkeller](https://github.com/avivkeller) -
  **Aviv Keller** <<me@aviv.sh>> (he/him) - [Support me](https://github.com/sponsors/avivkeller)
* [Ayase-252](https://github.com/Ayase-252) -
  **Qingyu Deng** <<i@ayase-lab.com>>
* [bengl](https://github.com/bengl) -
  **Bryan English** <<bryan@bryanenglish.com>> (he/him)
* [benjamingr](https://github.com/benjamingr) -
  **Benjamin Gruenbaum** <<benjamingr@gmail.com>>
* [BethGriggs](https://github.com/BethGriggs) -
  **Beth Griggs** <<bethanyngriggs@gmail.com>> (she/her)
* [bnb](https://github.com/bnb) -
  **Tierney Cyren** <<hello@bnb.im>> (they/them)
* [bnoordhuis](https://github.com/bnoordhuis) -
  **Ben Noordhuis** <<info@bnoordhuis.nl>>
* [BridgeAR](https://github.com/BridgeAR) -
  **Ruben Bridgewater** <<ruben@bridgewater.de>> (he/him)
* [cclauss](https://github.com/cclauss) -
  **Christian Clauss** <<cclauss@me.com>> (he/him)
* [ChALkeR](https://github.com/ChALkeR) -
  **Сковорода Никита Андреевич** <<chalkerx@gmail.com>> (he/him)
* [cjihrig](https://github.com/cjihrig) -
  **Colin Ihrig** <<cjihrig@gmail.com>> (he/him)
* [codebytere](https://github.com/codebytere) -
  **Shelley Vohr** <<shelley.vohr@gmail.com>> (she/her)
* [cola119](https://github.com/cola119) -
  **Kohei Ueno** <<kohei.ueno119@gmail.com>> (he/him)
* [daeyeon](https://github.com/daeyeon) -
  **Daeyeon Jeong** <<daeyeon.dev@gmail.com>> (he/him)
* [dario-piotrowicz](https://github.com/dario-piotrowicz) -
  **Dario Piotrowicz** <<dario.piotrowicz@gmail.com>> (he/him)
* [debadree25](https://github.com/debadree25) -
  **Debadree Chatterjee** <<debadree333@gmail.com>> (he/him)
* [deokjinkim](https://github.com/deokjinkim) -
  **Deokjin Kim** <<deokjin81.kim@gmail.com>> (he/him)
* [edsadr](https://github.com/edsadr) -
  **Adrian Estrada** <<edsadr@gmail.com>> (he/him)
* [ErickWendel](https://github.com/ErickWendel) -
  **Erick Wendel** <<erick.workspace@gmail.com>> (he/him)
* [Ethan-Arrowood](https://github.com/Ethan-Arrowood) -
  **Ethan Arrowood** <<ethan@arrowood.dev>> (he/him)
* [fhinkel](https://github.com/fhinkel) -
  **Franziska Hinkelmann** <<franziska.hinkelmann@gmail.com>> (she/her)
* [Flarna](https://github.com/Flarna) -
  **Gerhard Stöbich** <<deb2001-github@yahoo.de>> (he/they)
* [gabrielschulhof](https://github.com/gabrielschulhof) -
  **Gabriel Schulhof** <<gabrielschulhof@gmail.com>>
* [geeksilva97](https://github.com/geeksilva97) -
  **Edy Silva** <<edigleyssonsilva@gmail.com>> (he/him)
* [gengjiawen](https://github.com/gengjiawen) -
  **Jiawen Geng** <<technicalcute@gmail.com>>
* [GeoffreyBooth](https://github.com/GeoffreyBooth) -
  **Geoffrey Booth** <<webadmin@geoffreybooth.com>> (he/him)
* [gireeshpunathil](https://github.com/gireeshpunathil) -
  **Gireesh Punathil** <<gpunathi@in.ibm.com>> (he/him)
* [gurgunday](https://github.com/gurgunday) -
  **Gürgün Dayıoğlu** <<hey@gurgun.day>> (he/him)
* [guybedford](https://github.com/guybedford) -
  **Guy Bedford** <<guybedford@gmail.com>> (he/him)
* [H4ad](https://github.com/H4ad) -
  **Vinícius Lourenço Claro Cardoso** <<contact@viniciusl.com.br>> (he/him)
* [HarshithaKP](https://github.com/HarshithaKP) -
  **Harshitha K P** <<harshitha014@gmail.com>> (she/her)
* [himself65](https://github.com/himself65) -
  **Zeyu "Alex" Yang** <<himself65@outlook.com>> (he/him)
* [hybrist](https://github.com/hybrist) -
  **Jan Martin** <<jan.krems@gmail.com>> (he/him)
* [IlyasShabi](https://github.com/IlyasShabi) -
  **Ilyas Shabi** <<ilyasshabi94@gmail.com>> (he/him)
* [islandryu](https://github.com/islandryu) -
  **Ryuhei Shima** <<shimaryuhei@gmail.com>> (he/him)
* [jakecastelli](https://github.com/jakecastelli) -
  **Jake Yuesong Li** <<jake.yuesong@gmail.com>> (he/him)
* [JakobJingleheimer](https://github.com/JakobJingleheimer) -
  **Jacob Smith** <<jacob@frende.me>> (he/him)
* [jasnell](https://github.com/jasnell) -
  **James M Snell** <<jasnell@gmail.com>> (he/him)
* [jazelly](https://github.com/jazelly) -
  **Jason Zhang** <<xzha4350@gmail.com>> (he/him)
* [JonasBa](https://github.com/JonasBa) -
  **Jonas Badalic** <<jonas.badalic@gmail.com>> (he/him)
* [joyeecheung](https://github.com/joyeecheung) -
  **Joyee Cheung** <<joyeec9h3@gmail.com>> (she/her)
* [juanarbol](https://github.com/juanarbol) -
  **Juan José Arboleda** <<soyjuanarbol@gmail.com>> (he/him)
* [JungMinu](https://github.com/JungMinu) -
  **Minwoo Jung** <<nodecorelab@gmail.com>> (he/him)
* [KhafraDev](https://github.com/KhafraDev) -
  **Matthew Aitken** <<maitken033380023@gmail.com>> (he/him)
* [legendecas](https://github.com/legendecas) -
  **Chengzhong Wu** <<legendecas@gmail.com>> (he/him)
* [lemire](https://github.com/lemire) -
  **Daniel Lemire** <<daniel@lemire.me>>
* [LiviaMedeiros](https://github.com/LiviaMedeiros) -
  **LiviaMedeiros** <<livia@cirno.name>>
* [ljharb](https://github.com/ljharb) -
  **Jordan Harband** <<ljharb@gmail.com>>
* [lpinca](https://github.com/lpinca) -
  **Luigi Pinca** <<luigipinca@gmail.com>> (he/him)
* [Lxxyx](https://github.com/Lxxyx) -
  **Zijian Liu** <<lxxyxzj@gmail.com>> (he/him)
* [marco-ippolito](https://github.com/marco-ippolito) -
  **Marco Ippolito** <<marcoippolito54@gmail.com>> (he/him) - [Support me](https://github.com/sponsors/marco-ippolito)
* [marsonya](https://github.com/marsonya) -
  **Akhil Marsonya** <<akhil.marsonya27@gmail.com>> (he/him)
* [MattiasBuelens](https://github.com/MattiasBuelens) -
  **Mattias Buelens** <<mattias@buelens.com>> (he/him)
* [mcollina](https://github.com/mcollina) -
  **Matteo Collina** <<matteo.collina@gmail.com>> (he/him) - [Support me](https://github.com/sponsors/mcollina)
* [meixg](https://github.com/meixg) -
  **Xuguang Mei** <<meixuguang@gmail.com>> (he/him)
* [mhdawson](https://github.com/mhdawson) -
  **Michael Dawson** <<midawson@redhat.com>> (he/him)
* [MoLow](https://github.com/MoLow) -
  **Moshe Atlow** <<moshe@atlow.co.il>> (he/him)
* [MrJithil](https://github.com/MrJithil) -
  **Jithil P Ponnan** <<jithil@outlook.com>> (he/him)
* [ovflowd](https://github.com/ovflowd) -
  **Claudio Wunder** <<cwunder@gnome.org>> (he/they)
* [panva](https://github.com/panva) -
  **Filip Skokan** <<panva.ip@gmail.com>> (he/him) - [Support me](https://github.com/sponsors/panva)
* [pimterry](https://github.com/pimterry) -
  **Tim Perry** <<pimterry@gmail.com>> (he/him)
* [pmarchini](https://github.com/pmarchini) -
  **Pietro Marchini** <<pietro.marchini94@gmail.com>> (he/him)
* [puskin](https://github.com/puskin) -
  **Giovanni Bucci** <<github@puskin.it>> (he/him)
* [Qard](https://github.com/Qard) -
  **Stephen Belanger** <<admin@stephenbelanger.com>> (he/him)
* [RafaelGSS](https://github.com/RafaelGSS) -
  **Rafael Gonzaga** <<rafael.nunu@hotmail.com>> (he/him) - [Support me](https://github.com/sponsors/RafaelGSS)
* [RaisinTen](https://github.com/RaisinTen) -
  **Darshan Sen** <<raisinten@gmail.com>> (he/him) - [Support me](https://github.com/sponsors/RaisinTen)
* [Renegade334](https://github.com/Renegade334) -
  **René** <<contact.9a5d6388@renegade334.me.uk>>
* [richardlau](https://github.com/richardlau) -
  **Richard Lau** <<richard.lau@ibm.com>>
* [rluvaton](https://github.com/rluvaton) -
  **Raz Luvaton** <<rluvaton@gmail.com>> (he/him)
* [ronag](https://github.com/ronag) -
  **Robert Nagy** <<ronagy@icloud.com>>
* [ruyadorno](https://github.com/ruyadorno) -
  **Ruy Adorno** <<ruy@vlt.sh>> (he/him)
* [santigimeno](https://github.com/santigimeno) -
  **Santiago Gimeno** <<santiago.gimeno@gmail.com>>
* [ShogunPanda](https://github.com/ShogunPanda) -
  **Paolo Insogna** <<paolo@cowtech.it>> (he/him)
* [srl295](https://github.com/srl295) -
  **Steven R Loomis** <<srl295@gmail.com>>
* [StefanStojanovic](https://github.com/StefanStojanovic) -
  **Stefan Stojanovic** <<stefan.stojanovic@janeasystems.com>> (he/him)
* [sxa](https://github.com/sxa) -
  **Stewart X Addison** <<sxa@redhat.com>> (he/him)
* [targos](https://github.com/targos) -
  **Michaël Zasso** <<targos@protonmail.com>> (he/him)
* [theanarkh](https://github.com/theanarkh) -
  **theanarkh** <<theratliter@gmail.com>> (he/him)
* [tniessen](https://github.com/tniessen) -
# GitHub 一般隐私声明

<!-- markdownlint-disable search-replace -->

## GitHub 隐私声明

生效日期：2026 年 4 月 27 日

欢迎阅读 GitHub 隐私声明。 声明介绍了我们如何处理您的“个人数据”，即与您直接关联或可能与您关联的信息。 声明适用于 GitHub, Inc. 或 GitHub B.V.,以“数据控制者”的身份，在您与显示此声明的网站、应用和服务（统称为“服务”）进行交互时所处理的个人数据。 此声明不适用于不显示此声明的服务或产品，例如相关的预览。

### 最终用户通知：组织提供的 GitHub 帐户

当学校或雇主为您提供 GitHub 帐户时，即承担在我们的服务中所使用的大多数个人数据的数据控制者这一角色。 这使得他们能够：

* 管理您的 GitHub 帐户，包括调整隐私设置。
* 访问和利用您的个人数据，其中包括与您如何服务相关的详细信息，以及您的内容和文件。

如果您是通过由组织（例如，您的雇主或学校）提供的帐户访问 GitHub 服务，则该组织成为数据控制者，而此隐私声明对您的直接适用性发生变化。 即便如此，GitHub 还会不遗余力地保护您的隐私权。 这种情况下，GitHub 充当数据处理者，在处理您的个人数据时遵守数据控制者的相关说明。 数据保护协议监管 GitHub 与数据控制者之间的关系。 请参阅为您提供帐户的组织的隐私声明，进一步详细了解有关其隐私做法。

如果组织授予您权限访问 GitHub 产品，则 GitHub 仅充当具体处理活动的数据控制者。 在与您的组织签订的合同协议中对此类活动有明确的定义，此协议称为数据保护协议。 可在 [GitHub 数据保护协议](https://github.com/customer-terms/github-data-protection-agreement)处查看我们的标准数据保护协议。 此声明出于上述有限用途监管对您个人数据的处理。 使用 GitHub 产品的所有其他方面遵守您组织的相关策略。

### 第三方访问和数据保护

当您使用第三方扩展、集成或在我们的服务中跟踪引用和链接时，相应第三方的隐私策略适用于您提供或同意与其共享的任何个人数据。 其隐私声明将会监管如何处理这些数据。

## 我们收集的个人数据

我们直接从您那里收集个人数据，自动从您的设备以及从第三方。 当您使用服务时，GitHub 处理的个人数据取决于多种变量，例如您与我们服务的交互方式（如通过 Web 界面、桌面或移动应用），您使用的功能（如接取请求、Codespace 或 GitHub Copilot），以及您使用哪种方法访问服务（您首选的 IDE）。 我们以下方详细说明了我们通过每种渠道收集的信息：

### 从您那里收集的

* 帐户数据：当您打开帐户时，我们会收集特定信息，例如，GitHub 句柄、姓名、电子邮件地址、密码、付款信息和交易信息。
* 用户内容和文件：当您使用我们的服务时，我们会收集个人数据作为您提供信息的一部分，如代码、输入、AI 输出、文本、文档、图像或反馈。
* 人口统计信息：某些情况下，您会向我们提供种族、性别或类似的人口统计详细信息。
* 反馈数据：此类数据由您通过调查、评论或交互式功能提交的信息组成。
* 付款信息：对于付费订阅，我们收集姓名、帐单邮寄地址和付款详情。
* 个人资料信息：我们收集信息用于创建用户个人资料，其中可能包含照片、其他电子邮件地址、职务或个人简介。
* 销售和市场营销数据：其中包括为促销通信提供的信息，如姓名、电子邮件地址和公司名称。
* 支持数据：当您寻求客户支持时，我们收集代码、文本或多媒体文件等详细信息。

### 自动收集的

* 按钮、工具，以及由其他公司提供的内容：我们的服务可能包含指向 Twitter 或领英等第三方服务的链接或按钮。 使用此类功能可能会出现数据收集的情况。 与此类按钮、工具或内容互动可能会自动将某些浏览器信息发送给相应公司。 有关详细信息，请查看这些公司的隐私声明。
* 必要 Cookie 和类似的跟踪技术：当您使用我们的服务时，我们使用 Cookie 和类似技术提供存储设置和识别等必要功能。
* 非必要 Cookie：根据您所在的管辖权地，我们可能会使用在线分析产品，此类使用 Cookie 帮助我们分析去标识化的用户如何使用我们的服务，并在您使用服务时增强您的体验。 我们还有可能采用第三方 Cookie 来收集数据，用于投入基于兴趣的广告。 在某些管辖权地，我们在获得您同意后仅使用非必要 Cookie。 有关更多详细信息和控制选项，请参阅[本](#what-are-your-cookie-choices-and-controls)部分。
* 电子邮件市场营销交互：我们的电子邮件可能包含 web 信标，用于提供与您的设备类型、电子邮件客户端、电子邮件接收、打开次数和链接点击数相关的信息。
* 地理位置信息：根据服务的功能，我们会收集区域地理位置数据。
* 服务使用量信息：我们收集与您与服务交互相关的数据，例如 IP 地址、设备信息、会话详细信息、请求的日期和时间、设备类型和 ID、操作系统和应用版本、与您对存储库的贡献相关的信息，以及服务的特定功能的性能。
* 网站用法数据：我们收集与您的网站交互相关的日志数据，其中包括引用的网站、访问日期和时间、查看的页面，以及点击的链接。

### 来自第三方的

* 来自服务的其他用户的信息：其他用户可能会在提交问题和评论时共享与您相关的信息。 如果您被标识为您公司帐户的代表或管理员，则我们可能还会收到关于您的信息。
* 公开可用来源：我们可能从公开可用来源获取与您相关的信息。
* 链接到您 GitHub 帐户的服务：当您或您的管理员将第三方应用或服务与我们的服务集成时，我们会收到基于您对这些服务进行的设置的信息。 其中可能包括 Google 身份验证等服务提供的您的姓名和电子邮件等详细信息。 我们收到的信息取决于第三方的设置和隐私策略。 请始终查看这些内容以了解与我们的服务共享哪些数据。
* 供应商、合作伙伴和关联公司：我们可能会出于本声明中概述的目的，从供应商、经销商、合作伙伴或关联公司等第三方处收到关于您的信息。

## 处理目的：我们如何使用您的个人数据

我们处理的个人数据取决于您以何种方法访问我们的服务并与其进行交互，其中包括界面（Web、桌面、移动应用）、使用的功能（拉取请求、Codespace、GitHub Copilot），以及您首选的访问工具（例如您的 IDE）。 本部分详细介绍了 GitHub 处理您的个人数据时可能会用到的方法：

* 业务运营：我们在开展计费、会计和薪酬等活动时使用个人数据。 其中包括创建合并统计信息数据供内部报告、财务报表、收入计划、容量计划和预测模型（包括产品策略）等使用。
* 通信：我们使用个人数据通知您新的服务、功能、优惠、促销，以及其他相关信息。 还可能包含发送确认、发票、技术通知、更新、安全警报和管理消息。
* 推理：我们从收集到的其他数据生成新的信息以获得可能的偏好设置或其他特征。 例如，我们根据您的 IP 地址推理您大体所处的地理位置。
* 个性化：我们使用个人数据针对您的首选设置来自定义服务，评估企业业务广告和促销通信的效果，并确保提供无缝且一致的用户体验。
* 安全和保护：为了提升服务整体的安全性、完整性和保护措施，我们在处理个人数据时同时使用自动和手动技术（有时）进行滥用尘风检测、阻止，以及违反服务条款的行为。
* 服务预配：我们使用个人数据交付和更新您配置和使用的服务，并持续提供个性化体验和建议。
* 故障排除：我们使用个人数据识别和解决技术问题。
* 持续服务性能：个人数据可帮助我们使服务保持最新和高性能，并满足用户工作效率、可靠性、功效、质量、隐私、辅助功能和安全等各项需求。
* 产品开发和改进：我们使用个人数据开发和改进我们的产品、服务和技术，包括人工智能和机器学习技术。 这包括改进功能、开发新产品、增强安全性和安全功能以及训练模型。 我们会采取适当的技术保护措施，包括在可行情况下使用数据聚合和去标识化技术，在实现这些改进的同时保护您的隐私。
* 遵守和解决法律业务：包括响应 GitHub 作为控制者处理的个人数据的数据主体请求（例如，网站数据）、税务要求、协议以及争议。
* 提供专业服务：我们使用个人数据来提供培训、咨询或实现（“专业服务”）。 其中包括提供技术支持、职业规划、建议、指导、数据迁移、部署，以及解决方案/服务开发服务。
* 改进专业服务：根据提供专业服务时发现的问题，提高专业服务和其下产品的交付、功效、质量和安全性，包括修复软件缺陷以及用其他方式让专业服务保持最新和高性能。

开展这些活动时，GitHub 会采取数据最小化做法并使用所需的最小量个人信息。

## 个人数据的共享

我们可能会与以下接收者共享个人数据：

* 滥用和欺诈预防实体：我们可能会出于善意，在认为有必要的情况下披露个人数据以阻止对于我们服务的欺诈、滥用或攻击，或保护 GitHub 和我们用户的安全。
* 关联公司：个人数据或与 GitHub 关联公司（包括Microsoft）共享，以促进客户服务、营销和广告、订单履行、计费、技术支持、法律和合规性义务、产品开发和改进（包括培训和改进人工智能和机器学习技术），以及各自的隐私声明中所述的其他目的。 当我们与关联公司共享数据时，他们将根据适用的法律及自身隐私承诺对数据进行处理。
* GitHub 组织帐户：如果组织将您添加到其 GitHub 帐户，我们可能会与该组织共享个人数据以履行商业关系。 这种情况下，您对服务的使用受到您的组织和 GitHub 之间签订的数据保护协议和条款的保护。
* 主管部门：我们可能出于响应法律要求或保护自身权利和安全之目的，将个人数据披露给经授权的执法部门、监管部门、法庭或其他公共机构。 有关详细信息，请参阅我们的[用户数据法律要求指导准则](https://docs.github.com/en/site-policy/other-site-policies/guidelines-for-legal-requests-of-user-data)。
* 公司交易实体：我们可能会在法律限定范围内，依据本隐私声明之规定，出于销售或合并等战略业务交易之目的披露个人数据。
* 合作伙伴和经销商：我们与为我们的服务提供销售、咨询、支持和技术服务的第三方开展合作。 情况允许且在需要时获得您同意后，我们可能会与这些合作伙伴和经销商共享您的数据。
* 子处理方和服务提供方：我们可能使用供应商代表我们提供服务，其中包括托管、市场营销、广告、社交分析、支持票证、信用卡处理或安全服务。 这些服务需遵守合同义务，以确保您信息的安全、隐私和保密。 请访问 <https://docs.github.com/en/site-policy/privacy-policies/github-subprocessors>，查看我们的子处理方名录。
* Visual Studio Code (GitHub Codespaces)：GitHub Codespaces 和 github.dev 在 Web 浏览器中提供 Visual Studio Code，默认收集其中一些遥测。 有关遥测收集的详细信息，请参阅 [VS Code 网站](https://code.visualstudio.com/docs/configure/telemetry)。 若要选择退出，请转到 VS Code 左上角菜单中的“文件 > 偏好设置 > 设置”。 选择退出会同步 GitHub Codespaces 和 github.dev 中所有未来 Web 会话的这项偏好设置。
* 其他第三方应用：我们可能根据您的指示与我们商城中提供的第三方应用共享个人数据。 您对指示我们与这些应用共享的数据负责。
* 其他用户和公众：根据您的帐户设置，我们可能会与服务的其他用户和公众共享个人数据。 您控制公开哪些信息。 若要调整设置，请访问个人资料中的“用户设置”。 请注意，您在协作情境下共享的任何信息都有可能变为可供公众访问。

## 专用存储库：GitHub 访问权限

如果您的 GitHub 帐户包含私有存储库，则我们访问私有存储库信息的能力和权限参见《GitHub 服务条款》第 E 节（私有存储库）。

## 处理个人数据的法律依据（适用于欧洲经济区和英国最终用户）

GitHub 根据 GDPR 处理个人数据，确保每一次处理活动都有法律依据。 根据数据类型和上下文（包括您如何访问服务），依据有所不同。 我们的处理活动通常遵循以下法律依据：

* 合同必要性：根据 GitHub 服务条款，需要进行处理才能履行我们对您的合同义务。
* 法律义务：在必需遵守适用法律或为了保护 GitHub、我们的关联公司、用户或第三方的权利、安全和财产时，我们会处理数据。
* 合法利益：我们出于满足自身合法利益的目的处理数据，例如确保我们的服务安全、与您进行沟通，以及研发和提升我们的服务水平，这包括人工智能和机器学习技术。 仅您的数据保护权利或基本权利和自由高于这些权益时才会这样做。
* 同意：我们在您明确同意开展此类处理时处理数据。 当我们依赖于同意作为法律依据时，您有权随时辙回您对数据处理的同意。 本声明详细介绍了辙回流程，可访问我们的网站查看。

## 您的隐私权

根据您的居住位置，您可能对自身的隐私仅享有特定法律权利：

* 有权访问收集的与您有关的数据
* 有权请求获取与我们过去 12 个月内收集的个人数据的具体类型相关的详细信息，包括出于商业目的披露的数据
* 在某些情况下，有权校正或更新不准确或不完整的个人数据
* 特定条件下，有权擦除或限制处理您的个人数据
* 依据适用法律，有权拒绝处理您的个人数据
* 当处理是依据您的同意时，有权辙回同意
* 当技术上可行时，有权以结构化、常用和计算机可读取的格式，接收您收集的个人数据，以便于数据传输给另一家公司

若要行使上述权利，请发送电子邮件到 privacy\[at]github\[dot]com，按照提供的说明进行操作。 我们可能会出于安全考虑，请求您提供其他信息来验证您的身份，然后再解决您的数据相关请求。 请联系 dpo\[at]github\[dot]com，联系我们的数据保护官员提供任何反馈或问题。 根据您的所在区域，您有权向当地数据保护机构进行投诉。 欧洲地区用户可在欧洲数据保护委员会官网上找到机构联系方式，英国用户可访问信息委员的办公室网站。

我们希望遵守法律要求，做到快速响应请求。 请注意，我们可能出于法律义务或建立、发起或辩护法律索赔之必要而保留某些数据。

## 国际数据传输

GitHub 在世界各地多个位置存储和处理个人数据，包括您所在的当地区域、美国，以及 GitHub、其关联公司、子公司或子处理方开展运营活动所在的其他国家和地区。 我们将个人数据从欧盟、英国和瑞士传输到尚未达到欧盟委员会确定的数据保护水平的国家/地区。 当我们进行此类传输时，我们一般依赖欧盟委员会根据[委员会执行决定 2021/914](https://eur-lex.europa.eu/eli/dec_impl/2021/914/oj) 发布的标准合同条款，在数据传输中帮助保障您的权利和保护您的数据。 若要详细了解欧盟委员会关于在 GitHub 处理个人数据的国家/地区保护个人数据的充足性的决定，请参阅[欧盟委员会网站](https://commission.europa.eu/law/law-topic/data-protection/international-dimension-data-protection/adequacy-decisions_en)上的这篇文章。

## 数据隐私框架 (DPF)

GitHub 还符合美国商务部制定的欧盟-美国数据隐私框架（欧盟-美国 DPF）、对欧盟-美国 DPF 的英国扩展以及瑞士-美国数据隐私框架（瑞士-美国 DPF）。 GitHub 已向美国商务部认证，在根据欧盟-美国 DPF 处理从欧盟接收的个人数据，以及根据对欧盟-美国 DPF 的英国扩展处理从英国（和直布罗陀）接收的个人数据时，遵守欧盟-美国数据隐私框架原则（欧盟-美国 DPF 原则）。 GitHub 已向美国商务部认证，在根据瑞士-美国 DPF 处理从瑞士接收的个人数据时，遵守瑞士-美国数据隐私框架原则（瑞士-美国 DPF 原则）。 如果本隐私声明的条款与欧盟-美国 DPF 原则和/或瑞士-美国 DPF 原则之间有任何冲突，应以原则为准。 要了解有关数据隐私框架 (DPF) 计划的更多信息和查看我们的认证，请访问 <https://www.dataprivacyframework.gov/>。

GitHub 负责处理根据数据隐私框架 (DPF) 原则接收的个人数据，随后会传输给代表 GitHub 的第三方代理。 根据 DPF 原则，如果 GitHub 的代理以不符合 DPF 原则的方式处理此类个人数据，GitHub 仍应承担责任，除非 GitHub 证明其不对造成损害的事件负责。

### 争议解决流程

根据欧洲美国 DPF、英国对欧盟美国 DPF 的扩展，以及瑞士美国 DPF，GitHub 会努力解决 DPF 与我们收集和使用您个人信息相关的 DPF 原则相关投诉。 欧盟、英国和瑞士地区的个人若要查询或投诉我们根据欧盟美国 DPF、英国扩展以及瑞士美国 DPF 接收的对于个人数据的处理，应先联系 GitHub：dpo\[at]github\[dot]com。

如果您没有收到我们对您的 DPF 原则相关投诉的及时确认，或者如果我们对您的 DPF 原则相关投诉的处理没有令您满意，请访问 <https://go.adr.org/dpf_irm.html> 了解更多信息或提出投诉。 国际争议解决中心的服务免费提供。

在某些情况下，个人有可能对任何其他 DPF 机制未解决的关于 DPF 合规性的投诉援引有约束力的仲裁。 有关其他信息，请访问 <https://www.dataprivacyframework.gov/framework-article/ANNEX-I-introduction>。

### 政府强制措施

GitHub 受联邦贸易委员会 (FTC) 的调查和强制措施权的约束。 根据《联邦贸易委员会法》第 5 条（15 U.S.C. 第 45 条），一个组织未能遵守执行 DPF 原则的承诺，可能会被联邦贸易委员会指责为欺骗。 联邦贸易委员会有权通过行政命令或寻求法院命令来禁止这种虚假陈述。

## 安全性和保留

GitHub 使用适当的管理、技术和物理安全控制措施来保护个人数据。 只要您的帐户处于活动状态且根据法律要求需要履行合同义务、解决争议和强制执行协议，我们就会保留您的个人数据。 保留期限取决于数据收集的目的以及任何法律义务。

## 安全性

GitHub 使用适当的管理、技术和物理安全控制措施来保护个人数据。

## 联系我们

请通过联系人窗体或发送电子邮件到我们的数据保护官员 dpo\[at]github\[dot]com，联系我们。
我们的地址：

GitHub B.V.
Prins Bernhardplein 200, Amsterdam 1097JB The Netherlands

GitHub, Inc. 88 Colin P. Kelly Jr. St. San Francisco, CA 94107 美国

## 未成年人的信息

我们的服务对象不包含未 13 周岁的个人。 我们不会有意收集此类个人的个人数据。 如果您发现有未成年人向我们提供了个人数据，请[通知我们](https://support.github.com/contact/privacy)。

## 隐私声明更改

GitHub 可能会定期修改此隐私声明。 如果对声明进行了重大更改，我们将至少提前 30 天通过更新网站或向与 GitHub 帐户关联的主电子邮件地址发送电子邮件来通知您。

## 翻译版本

以下是本文档其他语言的翻译版本。 如果其中任何版本与英语版本之间存在任何冲突、不确定或明显的不一致，以本英语版本为准。

### 法语

Cliquez ici pour obtenir la version française: [Déclaration de confidentialité de GitHub (PDF)](/assets/images/help/site-policy/github-privacy-statement\(07.22.20\)\(fr\).pdf)。

### 其他翻译版本

如需获取本声明的其他语言翻译版本，请访问 <https://docs.github.com/>，并在下拉菜单中选择位于“English”（英语）下方的某种语言。

## 我们对 Cookie 和跟踪技术的使用

### Cookie 和跟踪技术

GitHub 使用 Cookie 来提供、保护和改进我们的服务或开发我们服务的新特性和功能。 例如，Cookie 可用于 (i) 让您保持登录状态 (ii) 记住您的偏好 (iii) 出于安全和欺诈目的标识您的设备，包括根据需要维护我们服务的完整性 (iv) 搜集统计报告 (v) 为 GitHub 未来的发展提供信息和见解。 我们提供了关于 [GitHub 上的 Cookie](/zh/site-policy/privacy-policies/github-cookies) 的更多信息，其中阐述了我们设置哪些 Cookie、我们需要使用这些 Cookie 的原因，以及这些 Cookie 的有效期限。

对于企业营销页面，我们还可能使用非必要的 Cookie 来 (i) 收集企业用户的兴趣和在线活动的相关信息以个性化体验，包括让用户看到或收到相关性更高的广告、内容、推荐和营销 (ii) 投放有针对性的广告和开展其他营销工作并衡量效果。 如果在企业营销页面上禁用非必要的 Cookie，您看到的广告、内容和营销可能不太相关。

我们发送给用户的电子邮件中可能会包含像素标签，这是一种小型清晰图像，可告知我们您是否打开过电子邮件以及您的 IP 地址是什么。 我们使用该像素标签是为了更有针对性地向您发送电子邮件，并确保不会向您发送您不希望收到的电子邮件。

Cookie 在您的浏览器或设备上保留的时长取决于它是“持久性”Cookie 还是“会话”Cookie。 会话 Cookie 只会在设备上保留到您停止浏览为止。 持久性 Cookie 会一直保留，直到它们过期或被删除。 适用于持久性 Cookie 的到期时间或保留期取决于 Cookie 收集的目的和使用的工具。 您可能能够删除 Cookie 数据。 有关详细信息，请参阅“[GitHub 一般隐私声明](/zh/site-policy/privacy-policies/github-general-privacy-statement#what-are-your-cookie-choices-and-controls)”。

#### 什么是 Cookie 和类似技术？

我们使用 Cookie 和类似技术（例如网络信标、本地存储和移动分析）来运营和提供服务。 在访问企业营销页面（如 resources.github.com）时，这些 Cookie 和其他 Cookie（如广告 ID）可能会用于销售和营销目的。

Cookie 是浏览器在设备上存储的小型文本文件。 稍后当浏览器连接到同一网域中之前在设备上放置 Cookie 的网络服务器时，网站便可读取该 Cookie。 Cookie 中的文本包含一串数字和字母，可以唯一标识设备，也可以包含其他信息。 因此，在一段时间过后，浏览器每次连接到网络服务器时，该网络服务器都能识别该浏览器。

网络信标是包含在网站或电子邮件中的电子图像（也称为“单像素”或“透明 GIF”）。 浏览器打开包含网络信标的网页或电子邮件时，会自动连接到托管图像的网络服务器（通常由第三方运营）。 这样，网络服务器便可记录有关设备的信息，并设置和读取它自己的 Cookie。 同样，我们网站上的第三方内容（例如嵌入式视频、插件或广告）会导致您的浏览器连接到托管该内容的第三方网络服务器。

移动设备上的应用访问和使用用于分析的移动标识符的方式与网站访问和使用 Cookie 的方式大致相同。 因此，在移动设备上访问企业营销页面（如 resources.github.com）时，我们和我们的第三方分析和广告合作伙伴可以收集用于销售和营销目的的数据。

我们也可能使用所谓的“Flash Cookie”（也称为“本地共享对象”或“LSO”）来收集和存储与使用我们的服务有关的信息。 Flash Cookie 通常用于广告和视频。

#### 我们和我们的合作伙伴如何使用 Cookie 及类似技术？

GitHub 服务将 Cookie 及类似技术用于各种目的，包括存储您的偏好和设置、允许您登录、分析我们的服务的效果、跟踪您与服务的交互情况、开发推理、打击欺诈和履行其他合法目的。 其中一些 Cookie 和技术可能由第三方提供，包括服务提供商和广告合作伙伴。 例如，我们的分析和广告合作伙伴可能会在我们的服务中使用这些技术来收集您在一段时间在我们的服务中进行的在线活动的相关个人信息（例如您访问的页面、单击的链接以及类似的使用信息、标识符和设备信息），以用于包括投放有针对性的广告等各种目的。 GitHub 将在我们向企业客户推销产品和服务的页面上（例如在 resources.github.com 上）放置非必要的 Cookie。

我们和/或我们的合作伙伴也出于这些目的与第三方共享我们收集或推断的信息。

下表提供了有关我们如何使用不同类型 Cookie 的其他信息：

| 目的        | 说明                                                                                                                                                      |
| :-------- | :------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 所需 Cookie | GitHub 使用所需的 Cookie 来执行基本的网站功能并提供服务。 例如，Cookie 用于允许登录、保存语言首选项、提供购物车体验、提高性能、在网络服务器之间路由流量、检测屏幕大小、确定页面加载时间、改善用户体验以及用于受众调查。 我们的网站正常运行就需要这些 Cookie。          |
| 分析        | 我们允许第三方使用分析 Cookie 来了解您如何使用我们的网站，以便我们可以进行改进。 例如，Cookie 用于收集有关您访问的页面以及完成一项任务所需的点击次数的信息。 我们还使用一些分析 Cookie 来投放个性化广告。                                       |
| 社交媒体      | GitHub 和第三方使用社交媒体 Cookie 根据您在 GitHub 网站上的社交媒体个人资料和活动向您展示广告和内容。 这可确保您在我们的网站和社交媒体上看到的广告和内容将更好地反映您的兴趣。 这也使第三方能够开发和改进他们的产品，他们可以在非 GitHub 拥有或运营的网站上使用这些产品。   |
| 广告        | 此外，GitHub 和第三方可使用广告 Cookie 根据您已经看过的广告向您展示新广告。 Cookie 还会跟踪您点击了哪些广告或在点击广告后进行了哪些购买。 其目的是完成支付操作并向您展示更相关的广告。 例如，Cookie 用于检测您何时点击广告，并根据您的社交媒体兴趣和网站浏览历史向您展示广告。 |

#### 您的 Cookie 选项和控制有哪些？

您有几个选项可禁用非必要的 Cookie：

1. **专用于 GitHub 企业营销页面**

   任何提供非必要 Cookie 的 GitHub 页面都会在页面的页脚中有一个指向 Cookie 设置的链接。 您可以随时通过点击该链接并更新设置来调整您的偏好。

   一些用户还可以通过 Cookie 同意横幅管理非必要 Cookie，包括接受、管理和拒绝所有非必要 Cookie 的选项。
2. **普遍适用于所有网站** 您可以使用各种广泛提供的工具来控制您在网络上遇到的 Cookie。 例如：

* 如果浏览器发送[请勿跟踪](https://en.wikipedia.org/wiki/Do_Not_Track) (DNT) 信号，GitHub 将不会设置非必要 Cookie，也不会加载设置非必要 Cookie 的第三方资源。
* 许多浏览器提供 Cookie 控件，可限制您在线遇到的 Cookie 类型。 查看您的浏览器的文档以了解更多信息。
* 如果您启用旨在阻止跟踪的浏览器扩展（例如 [Privacy Badger](https://en.wikipedia.org/wiki/Privacy_Badger)），则可能会禁用网站或第三方设置的非必要 Cookie。
* 如果您启用旨在阻止恶意内容的浏览器扩展（例如 [uBlock Origin](https://en.wikipedia.org/wiki/UBlock_Origin)），则会禁用非必要 Cookie，甚至会阻止设置非必要 Cookie 的内容。
* 您可使用全球隐私控制 (GPC) 来表明您的隐私偏好。 如果 GitHub 检测到来自您设备的 GPC 信号，GitHub 将不会共享您的数据（我们不会出售您的数据）。 要了解详细信息，请访问[全球隐私控制 - 掌控您的隐私](https://globalprivacycontrol.org/)
* 广告控制。 我们的广告合作伙伴可能会加入可通过简单方式选择退出广告定位的协会，访问方式如下：
* 美国：[NAI](http://optout.networkadvertising.org) 和 [DAA](http://optout.aboutads.info/)
* 加拿大：[加拿大数字广告联盟](https://youradchoices.ca/)
* 欧洲：[欧洲数字广告联盟](http://www.youronlinechoices.com/)

这些选项特定于您使用的浏览器。 如果您从其他设备或浏览器访问我们的服务，请从这些系统执行以上操作，以确保您的选项适用于您使用这些系统时收集的数据。

## 美国各州特定信息

本部分提供额外信息专门面向于具有明显不同的数据隐私法律和法规的美国的某些州的居民。 这些法律可能会在生效时为当地居民授予特定权利。 本部分所使用的术语“个人信息”等效于术语“个人数据”。

### 隐私权

以下权利在美国各州隐私法律中很常见：

* 知情权和更正权：您有权请求获取我们收集的与您相关的具体个人信息相关的详细信息，并有权更正不正确的信息。 您可以通过联系我们来行使此权利。 您还可以在设置中访问和编辑基本帐户信息。
* 有权知道数据接收者：我们出于数据存储和托管等合法的业务运营目的，与服务提供商共享您的信息。 有关详细信息，请参阅下面的“共享您的信息”。
* 有权请求删除：您保留请求删除您数据的权利，在几种情况下例外。 此类例外情况包括：我们需要保留数据以遵守法律义务、检测欺诈活动、调查滥用报告或违返服务条款的其他行为，或纠正安全问题。 收到您经过验证的请求后，我们会立即删除您的个人信息（除非在例外情况下），并指示我们的服务提供商也采取同样的行动。 我们在设计之初采用简短的保留条款。
* 有权及时响应：您可以在任何 12 个月的期限内免费提出两次请求。 我们承诺在 45 天内响应您的请求。 情况复杂时，我们可能会将响应时间延长 45 天。
* 非歧视：当您行使任何自身权利时，我们不会反对您。 相反地，我们鼓励您密切留意我们的隐私设置，并在遇到任何疑问时联系我们。

### 关于收集个人信息的通知

我们可能会收集与我们的网站访客和“服务”（包括 GitHub 应用、软件、产品或服务）用户相关的各种类别的个人信息。 这些信息包括标识符/联系人信息、人口统计信息、付款信息、商业信息、互联网或电子网络活动信息、地理位置数据、音频、电子、视觉或类似信息，以及从此类信息获取到的推理。

我们出于各种目的收集这些信息。 这些目的包括：识别辅助功能差距并有针对性地提供支持、促进多样性和代表、提供服务、故障排查、实施计费和安全等业务运营、改进产品和支持研究、通知重要信息、确保个性化体验，以及提升安全性。

### 行使您的隐私权

若要发出访问、删除、更正或选择退出请求，请发送电子邮件到 privacy\[at]github\[dot]com 并按照提供的说明进行操作。 在处理您的请求之前，我们可能需要验证您的身份。 如果您选择使用经过授权的代理来代表您提交请求，请确保代理具有您的签名权限或所需的律师权。

若要选择退出共享您的个人信息，可以在我们的网站上单击“不要共享我的个人信息”链接，或使用全局隐私控制（“GPC”）（如可用）。 经过授权的代理还可以代表您提交选择退出请求。

### 加州

#### 强制披露

我们出于遵守加州隐私法的目的，还会披露以下信息：

* 我们在过去 12 个月收集了以下类别的个人信息：识别符/联系人信息、人口统计信息（例如性别）、与您关联的付款卡、商业信息、互联网或其他电子网络活动信息、地理位置数据、音频、电子、视觉或类似信息，以及从上述信息获得到的推理。
* 我们收集个人信息的来源包括：直接从您、自动收集、从第三方。
* 收集的个人信息的业务或商业目的总结如上，在处理目的下的隐私声明中有记录。
* 出于商业目的，我们在过去 12 个月披露了以下类别的个人信息：识别符/联系人信息、人口统计信息（例如性别和大致的地理位置）、付款卡、商业信息、互联网或其他电子网络活动信息、地理位置数据、音频、电子、视觉或类似信息，以及从上述信息获得到的推理。 我们向第三方业务合作伙伴和服务提供商、第三方网站可平台（如社交网络网站），以及我们隐私声明中“个人数据的共享”部分所述的其他第三方披露了每个类别的信息。
* 根据适用法律的定义，我们在过去 12 个月内“共享了”以下类别的个人信息：识别符/联系人信息、互联网或其他电子网络活动信息，以及从上述信息获取到的推理。 我们向/与广告网络、数据分析提供商和社交网络共享了每个类别的信息。
* 共享个人信息的业务或商业目的是协助我们开展市场营销、广告投放和受众衡量。
* 我们不“出售”或“共享”未年满 16 周岁的已知未成年人的个人信息。

#### 反客户信息披露法

根据《加州民法典》第 1798.83 条（也称为《反客户信息披露法》），向与个人建立业务关系的企业提供个人信息以用于个人或家庭目的的加州居民（“加州客户”）可能会要求提供有关企业是否出于第三方直接营销目的向任何第三方披露个人信息的信息。 请注意，我们不会出于本法所定义的任何第三方的直接营销目的向任何第三方披露个人信息。 加州客户可以通过发送电子邮件至 privacy\[at]github\[dot]com 请求提供有关我们遵守该法律的情况的更多信息。 请注意，企业必须每年对每位加州客户的一项请求作出回应，并且可能不需要对通过指定电子邮件地址以外的其他方式提出的请求作出回应。

#### 内容的删除

属于线上网站、服务或应用程序注册用户的 18 岁以下加州居民有权根据《加州商业及职业法典》第 22581 条删除或请求删除他们公开发布的内容或信息。 要删除您公开发布的内容或信息，[请提交隐私信息删除请求](https://support.github.com/contact/private-information)。 或者，要请求我们删除此类内容或信息，请将您希望删除的特定内容或信息的详细说明发送给 [GitHub 支持](https://support.github.com/request)。 请注意，您的请求并不保证完全或全面删除在线发布的内容或信息，并且在某些情况下法律可能不允许或不要求删除。 如果您对我们针对加州居民的隐私做法有任何疑问，请发送电子邮件到 privacy\[at]github\[dot]com。

我们珍视您给予的信任，在处理您的个人信息时始终心怀谨慎与尊重。 如果对隐私做法有任何疑问或担忧，请发送电子邮件至我们的数据保护官：dpo\[at]github\[dot]com。

### 科罗拉多州/康涅狄格州/弗吉尼亚州

如果您居住在科罗拉多州、康涅狄格州或弗吉尼亚州，则享有一些额外的权利。

* 如果我们拒绝您的权利请求，则您有权对判定提起上诉。 我们将为您提供必要的信息，以便届时提交上诉。
* 您有权选择退出分析，以进一步做出对消费者产生法律或类似重大影响的决定。 GitHub 不参与科罗拉多州法律定义的此类分析，因此无需选择退出。

### 内华达州

根据《内华达州修订条例》第 603A 章的规定，我们不会出售您所涵盖的信息。 如果仍对隐私声明中涵盖的信息或其他任何内容有疑问，请发送电子邮件至 privacy\[at]github\[dot]com。resources.github.com）时，我们和我们的第三方分析和广告合作伙伴可以收集用于销售和营销目的的数据。# 组织和企业的基于使用情况的计费

准备向Copilot业务 和Copilot Enterprise的基于使用情况的计费过渡。

<!-- expires 2026-06-01 -->

> \[!IMPORTANT]
> GitHub 将从 **2026 年 6 月 1 日起**使用本文中所述的计费方法。 可以阅读有关此更改的详细信息 [the GitHub Blog](https://gh.io/copilot-billing-blog)。

<!-- end expires 2026-06-01 -->

## 什么是 GitHub AI Credits？

GitHub AI Credits 是 Copilot 在 Copilot业务 和 Copilot Enterprise 中使用的计费单位。

当组织中的某人使用 Copilot时，交互会使用令牌：输入令牌（发送到模型的内容）、输出令牌（模型生成的内容）和缓存的令牌（上下文模型重用或存储）。 每个令牌都基于所使用的模型定价，总价格转换为 AI credits1 AI credit = $0.01 USD。

交互的成本取决于两个事项：模型和使用的令牌数。 使用轻型模型的快速聊天问题可能会花费额度的一小部分。 跨多个文件使用前沿模型进行复杂编码代理会话会花费更多，因为它执行了更多的工作。

## 在AI credits中如何计费？

Copilot使用 AI 模型的功能会消耗AI credits。 这包括 副驾驶聊天、 Copilot 命令行界面（CLI）、 Copilot云代理、 Copilot空间和 Spark第三方编码代理。

代码完成和接下来的编辑建议**不**在AI credits中计费。 对于所有付费计划，它们仍然不受限制。

## AI credits 如何工作？

每个分配的 Copilot 许可证每月都附带一个包含 AI credits 的 **金额**：

| Plan               | 每个用户每月的总次数AI credits |
| ------------------ | -------------------- |
| Copilot业务          | 1,900                |
| Copilot Enterprise | 3,900                |

用户的AI credits在计费实体级别被合并使用。 例如，拥有 100 Copilot业务 个用户的企业将获得 190,000 AI credits 个共享池，而不是 100 个单个存储桶。 这意味着，当用户需要时，电力用户可以吸引更多，而较轻的用户抵消了这种消耗。

在中途添加许可证会立即增加许可证池。 在计费周期中删除许可证不会缩小许可证池：减少将在下一个计费周期开始时反映。

<!-- expires 2026-09-01 -->

### 现有客户的促销金额

现有 Copilot业务 和 Copilot Enterprise 客户在前三个月的使用计费周期（2026 年 6 月 1 日至 9 月 1 日）将获得更多的 AI credits 包含额度：

| Plan               | 每个用户每月的总额AI credits |
| ------------------ | ------------------- |
| Copilot业务          | 3,000               |
| Copilot Enterprise | 7,000               |

促销期过后，基本使用量将恢复到上述标准额度。

<!-- end expires 2026-09-01 -->

## 如果我超出了AI credits的限额，会怎么样？

当您的池 AI credits 耗尽之后，接下来会发生什么，取决于您如何配置额外使用的策略。

* **允许的额外使用**：使用将按照发布的每信用点费率继续。 额外开支将记入您组织或企业的账户。
* **不允许额外使用**：在每月金额刷新之前，使用将被阻止，直到下一个计费周期。

如果您已设置用户级预算且用户已用尽预算，无论组织的池是否仍然有容量，该用户对Copilot 的访问都会被终止。 预算耗尽时，不会自动回退到低成本模型。

其他使用预算以美元为单位设置，使用情况会显示在 GitHub AI Credits内。
GitHub AI Credits 以固定费率绘制预算：1 AI credit = $0.01 USD，因此，10 美元的预算涵盖 1,000 个 AI 额度。

## 如何使用预算控制成本？

可以在四个级别设置预算来控制 GitHub AI Credits 支出：

* **企业级预算** 跟踪企业下所有组织、存储库和成本中心的支出。
* **组织级预算** 跟踪组织中所有存储库的支出。
* **成本中心级预算** 跟踪单个成本中心的支出。
* **用户级预算** 跟踪单个用户的支出。 $0 的用户级别预算意味着根本无法访问。

可以在接近限制时使用预算来获取警报，并在使用时强制实施硬性停止。 例如，如果想要允许一些额外的使用情况，但保持控制，则可以将用户级预算设定为稍微高于包含的限额。

有关设置预算的详细信息，请参阅 [设置预算以控制按流量计费的产品的支出](/zh/billing/how-tos/set-up-budgets)。

## 后续步骤

* 若要比较模型之间的按令牌成本并估算支出，请参阅 [模型和定价 GitHub Copilot](/zh/copilot/reference/copilot-billing/models-and-pricing)。
* 有关如何准备基于使用情况的计费的指导，请参阅 [为组织准备基于使用情况的计费](/zh/copilot/how-tos/manage-and-track-spending/prepare-for-usage-based-billing)。# GitHub Copilot计划

您可以了解 Copilot 的可用计划。

<!-- expires 2026-06-01 -->

> \[!IMPORTANT] 从 2026 年 6 月 1 日起， GitHub 从 Copilot 基于请求的计费转移到基于使用情况的计费。 请参阅 [组织和企业的基于使用情况的计费](/zh/copilot/concepts/billing/usage-based-billing-for-organizations-and-enterprises) 和 [个人基于使用情况的计费](/zh/copilot/concepts/billing/usage-based-billing-for-individuals)。

<!-- end expires 2026-06-01 -->

> \[!IMPORTANT]
>
> * **从 2026 年 4 月 20 日起**，新的注册Copilot ProCopilot Pro+和学生计划将暂时暂停。
> * **从 2026 年 4 月 22 日开始**，针对组织和Copilot业务GitHub Free计划的新自助注册GitHub Team暂时暂停。

GitHub 提供多个针对 GitHub Copilot 的计划，具体取决于你的需求，以及你是作为个人使用 Copilot 还是作为组织或企业的一部分。

* **GitHub Copilot 免费** 适用于未通过组织或企业获得 Copilot 访问权限的个人开发人员。 该免费计划包括对某些 Copilot 功能的有限访问权限，让您免费试用 AI 驱动的编码辅助功能。

* **GitHub Copilot 学生** 可用于已验证的学生。 该计划包含无限补全、访问 副驾驶聊天 中的高级模型、访问 Copilot云代理，以及每月高级请求额度。

* **GitHub Copilot Pro** 专为想要更多灵活性的个人设计。 此付费计划包含无限补全、访问 副驾驶聊天 中的高级模型、访问 Copilot云代理，以及每月高级请求额度。 经验证的教师和热门开放源代码项目的维护人员可能有资格免费访问。

* **GitHub Copilot Pro+** 除了 Copilot Pro 中的所有内容之外，还包括更大的高级请求额度，以及完全访问 副驾驶聊天 中所有可用的模型。 非常适合希望获得最先进功能的 AI 高级用户。

* **GitHub Copilot业务** 适用于使用 GitHub Free 或 GitHub Team 计划的组织，或使用 GitHub Enterprise Cloud 计划的企业。 此计划包含 Copilot云代理，并支持为组织成员集中管理和 Copilot 策略控制。

* **GitHub Copilot Enterprise** 适用于使用 GitHub Enterprise Cloud 的企业。 它包括Copilot业务的所有功能，并附加其他企业级功能。 企业所有者可以将Copilot Enterprise或Copilot业务分配给单个组织，或将Copilot业务直接分配给用户和团队。

Copilot 当前对 GitHub Enterprise Server 不可用。

## 比较 Copilot 计划

下表显示了每个 Copilot 计划中可用的功能。

<div class="ghd-tool rowheaders">

|                           | 免费Copilot                                                                                                                                                                                                                                                                                                                                                                                                                          | Copilot学生                                                                                                                                                                                                                                                                                                               | Copilot Pro                                                                                                                                                                                                                                                                                                             | Copilot Pro+                                                                                                                                                                                                                                                                                                            | Copilot业务                                                                                                                                                                                                                                                                                                               | Copilot Enterprise                                                                                                                                                                                                                                                                                                      |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 定价                        | 不适用                                                                                                                                                                                                                                                                                                                                                                                                                                | 免费                                                                                                                                                                                                                                                                                                                      |                                                                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                                         |
| 10 美元 每月<br>（对某些用户免费）     |                                                                                                                                                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                                         |
| 39 美元 每月<br>              | 每月每个分配的席位 19 美元                                                                                                                                                                                                                                                                                                                                                                                                                    | 每月每个分配的席位 39 美元                                                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                                         |
| 高级请求                      | 每月 50 次                                                                                                                                                                                                                                                                                                                                                                                                                            | 每月 300 次                                                                                                                                                                                                                                                                                                                | 每月 300 次                                                                                                                                                                                                                                                                                                                | 每月 1500 次                                                                                                                                                                                                                                                                                                               | 每月每位用户 300 次                                                                                                                                                                                                                                                                                                            | 每月每位用户 1000 次                                                                                                                                                                                                                                                                                                           |
| 以每次请求 0.04 美元的价格购买额外的高级请求 | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-x" aria-label="Not included" role="img"><path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="Included" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="Included" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="Included" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="Included" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="Included" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg> |

</div>

### 智能体

<div class="ghd-tool rowheaders">

| 智能体           | 免费Copilot                                                                                                                                                                                                                                                                                                                                                                                                                          | Copilot学生                                                                                                                                                                                                                                                                                                                                                                                                                          | Copilot Pro                                                                                                                                                                                                                                                                                                             | Copilot Pro+                                                                                                                                                                                                                                                                                                            | Copilot业务                                                                                                                                                                                                                                                                                                               | Copilot Enterprise                                                                                                                                                                                                                                                                                                      |
| ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Copilot云代理    | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octico1. 