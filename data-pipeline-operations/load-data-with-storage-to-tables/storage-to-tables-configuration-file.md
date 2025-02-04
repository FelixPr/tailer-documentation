---
description: >-
  This is the description of the configuration file of a Storage to Tables data
  operation.
---

# Storage to Tables configuration file

The configuration file is in JSON format. It contains the following sections:

* Global parameters: General information about the data operation.
* Source parameters: Information related to the data source provider.
* Destination parameters: Information about input file templates and destination tables. The "destinations" section will refer to [DDL files](storage-to-tables-ddl-files.md), which contain the schema of the destination tables.

## 👁🗨 Example

Here is an example of STT configuration file for a GCS to BigQuery transfer:

```text
{
  "configuration_type": "storage-to-tables",
  "configuration_id": "Load_sales_files_from_it",
  "environment": "DEV",
  "account": "000099",
  "activated": true,
  "archived": false,
  "short_description": "This Job load sales files sended by IT into the Orsay PSA",
  "doc_md": "Load_sales_files_from_it.md",
  "source": {
    "type": "gcs",
    "gcp_project_id": "fd-io-dlk-orsay",
    "gcs_source_bucket": "mirror-fd-io-exc-demo-wbd--n-in",
    "gcs_source_prefix": "testjul",
    "gcs_archive_prefix": "archive",
    "gcp_credentials_secret": {
      "cipher_aes": "22300825396fabbba6918c292ff3ec1a",
      "tag": "8dd3db4c71bfc2caa8b963d475d1bbd1",
      "ciphertext": "4c74df268d5a7541f8264c2e7a282fd4266ee7783ea7fcb23215db59428bb9bac64742df26afb2c13925c731f24525dff53b751b1363e2a5f5bb0b51d318f63dc3b970b52873a86afae0de8128dcddc82704578528d0f609e15c7938f4163b087d577aaf4f127347b3fa0eb336f76cd86097efcc471434323c84490adf93f4b3f24646f9901172563b8404fe6e599b15fc79f242c59d2cc8aebd389c73d462b541a5421fe92c6e7a8ad19d18396d10266c7764cd6704e981d56c96cc06d82f68c06243640d5572284b5f1e2a57ee5fa3a72098905b68f4ff86cdabadf7565f19cc6a95148a0b271e17b1977eac47a11542d68a7497f58c8e6a73ccc7f22dce0ed897429e58c56a0ab28943feed25321d7d2468afcffabd268729afdc782ff994187204249e4fb18b57c2023f25243dffc2bf4e927f317441bd58901457cd870068733b1be37bc56236efdb59e9dfe1607621af2ddf2830978836c523ec2be178d3ccac4e7e40233fa9b8296364454f4a2116e952c9b91372304f690b85b4c98ea4bbe41b55640d0e627e707f1a1a4f0ffe8c87e15d87e965a4e92759ef519b00bdc74890700ed4c42da75329eff93503e638ee0b9b4b37f34f65510af887be7193d9fd3635c238ba27b1ba4437a0e4c82238f81fcda8f7282f356b78eeb6049a43d1aeb25e446a6ea6730d1b5c1eaa0402bb654d703cd36d8d1f4b7e86cad85208a3252c9a47031939a06686f3a8151bdbf64fe0c2fc816e330334407136593b3cac87a1d467f6c5efc86a61622b76a28dac88d4bbc3883ccb8c5dcc6cda38f9e8eee111d5cb9751a2e04c801925c360c7b1be09298b599996e32361570a1066fa8a214dc65d19bf2d62b3f0aa752c2a9325d7d256539f2ba671307fdba19e0679c219101aa6716b3ce99ba5874a306d126efcf175795e75aa547641f2eccf5ca2c427dcb27a56f72629b5bba564032217f3539d854f45c63620094b0c30e25a67bde0452be966643436b364e578456c8fb8b7e7394fd8e0fa1a1ab7115626a062295450f2b4855421b41ae9aa7e969abbb36dd714460c56cd67955f7c453b1abb9a8175a2e419f1e97e1fa971626348a2930d5e28a14b9eef276d569f5b1398d1ac34052dfbe68c00a90fa7d76755daf9dcd44b2c7ad0bec0432368281228935e4f5663cfed92de2eee279b9f5e1143d9b2bbefdf0330e82247b437d9ef6ccf16b15509760b2b2c2c7d2ea48b7c6e9930db5c11aaeaeb2c9868f138c4cd825b2703c6272ed9a1536934d680b858a6db8291919e9f3c03b7f0ee12e8bc4b8ed190d7755cce32a76fb6c28fbcd2813c0ead9343447b3762436581fac0956bfeba9a585aaf88e45207024b3a73a56b7d87544504ad169e89145df2a7718948afe8f024de602a0ce097708de4b5587415c8f8b53f4ea907e0cc4ff09a5212f4a7a13a94351befa7a783581431394f0f11dc007f44d78e4b93527d302410f77646ce28144f26ab790bcff9e8fc6bc13bbd6a1076638b35ee1a2ad9eb56a9c832706ab26f61c9effda50c3dfdb70755e0637d9403780430b105b72d52fb91e2fa96cb125e928cf1d1819ac8b7081bf156b78e7879e61255f91ecf654316ab6e2b4d898cbee10f31b9a8a23896d0d8d90454ccfce73d823d4573bbea880ed17c1e233c25a4334a940f653f1684bbced80dde0deaedd7db8a03ed907071a9d4cb4199509a0f8af5d6169f5e849649b68719e126578bcde94ef84088419ca6c62b994d2a83d7b6ae83a434c45b4bdd33a6e0fd07dc3ca181d7ae19186ce06b166ca3c5eab20c45774c1340c2bc65c8bb005b1c715dd3db9cdddb776ad61865dc7401b6276bee760064fcae83bf8e3cb6d88445a514cb82d67fea5d4d40211425b87cc15e2c21b2e9328f593df9ad1867edbedb90501cb563f4a2d0f3ef20560db1624b1f4fa7776d2040fbfd8a6eca256f4098934f99ee6b219d4feb696d5b69b5267d0494f0dcb1195ece5ca587f253906e0733b7aa830087c3ea293dbe408644288500b387208e74fc4ebfcf08bfd01b0af5bf44ef4462fd73c8aeff752300f746130c9a65c8fabcd1aa8ca6075b748034a3fe36eaa19f0f4f437400598c920233515d496cd5f8ebd805999c75e8aa7a29deb514eadc50e6fe3429d60e481127a06c8c9d6719e636f6644c47cfca6c97a4488ffb93c4a3b139e8122c93b3d5a3c6f2aebc5f3c39a3f8fa061ac4368b635c63510f72238823f61740727d1be2cc4e0c8eaafea8e83356445b3dc58e7cd32542b261ebe880a3dc9f7ac9d3e455485bfbba596bbf3d6cc6d1f32e885acf3d72aa569c80e5a3783c1c97a66e4ced4f99219d85778795e0cefaaa478f8ba313983609b0a788293cee51fe5cf57a725fbc93452381ac8046c140df659e73d96901665c1b2a9a2b150152da3dca803bb11ec42e83a2c77885f05e5bf0473a6ccc3ba2e0901ce45ccdf8a8ba1a37164ac257c81013348f2ef34e49846d60de5d4ba172063b49caffe49822bd4c766f598e74946cbd394b5d12680fd5645e8028b217f3d0a3fa84b7bb78d8ec8bfe1ef76913aafd6b1c57237be153281252b02dfbaf456eaebde69336f9fafb3de04ba35fdae5a598aaf5d901c8b25584e676d674b8907151679d5160c7f2790dac2d0f232e6394ff9cd9bfdb8ff35bc797e7b908dd22dc5929b0387757499b97218f9610e334c5e1a79f7e26441a3e590881f4f63138fa4d3e20e6c3863d62ef9e8e2abecead576df82247ba61b54c2d2bf1b781ec43b9f6c097b99122fd7b95e3ff471f270c22a048165b24a132964c2c8bdc4c3a46c599d9b905cb69f9623dd3c3529a8794b859ae9e49fc4bcf8cbf3cb9b4ff999df26355a0c19dad0891c3af260bf7a979ce6e905180556172ceee81accf85b031e6b10727adb42db266b582749e911250cf0e165b713c8e8871653629991a661ef2770f32c1afae7908581c882393a65653be163f0216800fbed71b5376021acd8170c6b53b4f42db5eeec3110f97a4c4dcc52c173846474a821f1549a698e6541a3ce6ed7db62b8fe8d65f694dcb4cb6b767483a8b49f3966dc2488a3898334095f526456e47eb67a10d9b105767b96fee9c44c12b4fc51c4e0abfe6451530c7409a3f84ea36ea0114036940123fbd50000a23150b7043df22c4a9b08b47dcb1458fc1a8c6a59c19beb019c6852eb2f5cb6e984a57eb6395b75d5f6c2e53d5317b518e59682018f925453843c7876bdf3f5d74c1c6e1abc3793610f6bc60c974d2358ffa101b912913a4afa3b839238b11f78edc99f3da31b31bc181abe99d8b49c6c73978a99f41e20b1da2b95dc316a8b74ec09d8b01b3c7f7c1ec95bf28543d9ecda9104fe0448ed034225d30c5d829ce52836f26661e1971d83c3b4fa86125df73f1210cd232ee0ad3eaca922d2ffd18958412e77082226d45535d68c27b3ca4b545cd86c415c51c0f47301cd4128d8813356bf6c7db483e0870e723c07848cfd6937b8473966edf6ae4c60d39846495aa5e8aaac193e296cddf5a6db3960dc68c6cc2ef04bf29cf727360e1b0d2d86f5a0f809ceb5ae547006b340d31f83eeaddfd1e1a65585a92f00e38418c628580316ee659260a25449a7f9256ab52872f2b3ece03ab2b1d21f87d68bd3a8f7b03df6f861502c46ebb76d10c38aedbb8d21ff7929c254c7b20bf0a114d2ed13c068734bc2cfc351d2dd3fd9107a3d37e65aa22d11982f995fdb453d093552e511cb77ebe43e8f9f5fabf04389a40824156fa1ceb802c2d6c620a8b71eab15214dbee3412aa7d9f193a14b0875c6dd6297c1eced20aa9f1fc1816e19b85b4ad26e5a71c463a58dcdf2bfb85b606540c6013eda834863b6990a1587d807231fa71e9f37be94f4302ce51ddd18486bdf030b2cd521ba1aabfe6b6ce4b387858e6d17c2097a8b0d3e3bb19b2b8712e400afede0f0c2fc7efb7350aaafe02ef78446c35d49c9d924806efe3dd64343eaf007692c6d08c9ad7750fbb79a0fee805e458a4835b91298b33993cfa871dc52fec7bea6532f046308c9c04e1f0683fdf463e2c144c0ec40bf87260ea178a203c1bf1624b092e1e0091cac5729d522e5e548a23a68df02e23920db605bad77dca8517bc841732f79e64e89bf21ed84746bfd643bf2b3b6457caff80c6449e6a8b82244133a9cbaf983b4b1786d05b8f8c11b6801bd7e81b18974626d014d7bf5112ef2ae576eb18000d8cb8828f126f5ed08677cd51ecab72251c5acf4c38055c8e3811b3987f76583431261230d1bab65dfb5723e8d1d565dbd0f001df0f6197b3347b678d718aad6efb0fc6a7bac833fb1b4c1f0148362161ad2353dd53db23a0334341420c57f893ca2ea9cb1094c8f530495d7a5e14eff81913c4c3a94746c0827a28ec63383f71ae5c1d3869d6fb71209982af029bf897332e5662f1dd04e88d54e2e4ae",
      "enc_session_key": "830606cbc4f9401a29c7977d364398a4e3e0b27a7ee2d94263e271b4523bd5f6badcfd8811d50ebb2370847c9a854d84d84008bdbaffaa01a539bc24fb6cf819102a0412eb20d44c13165fea31a49cea13b46df49670327f760a5a1606e42aef93a70ade8acd454ef4b661ae8442033a56dce5b5c29a8747af08523693ff4d226dba48709a7832ab3fb06536a88fb7f80a9ce03c58ea0ad3757864ec5edb0f8a365e078712489ac95f522062d9d7619009bed727d1d4f2c486d53dfd2e27cafce7734c81a190701bc1a556eea2d265d15a9df388c41d979ee57aa9cd25a1ecfc557ae4a31fbd7c7da0e5bc6ece5ceddfc61e73c98ae24b731cf846a0648dc93b"
    }
  },
  "destinations": [
    {
      "type": "bigquery",
      "gcp_project_id": "fd-io-dlk-orsay",
      "gbq_dataset": "dlk_demo_wbd_psa",
      "source_format": "CSV",
      "create_disposition": "CREATE_IF_NEEDED",
      "write_disposition": "WRITE_TRUNCATE",
      "skip_leading_rows": 1,
      "field_delimiter": "|",
      "gcp_credentials_secret": {
        "cipher_aes": "22300825396fabbba6918c292ff3ec1a",
        "tag": "8dd3db4c71bfc2caa8b963d475d1bbd1",
        "ciphertext": "4c74df268d5a7541f8264c2e7a282fd4266ee7783ea7fcb23215db59428bb9bac64742df26afb2c13925c731f24525dff53b751b1363e2a5f5bb0b51d318f63dc3b970b52873a86afae0de8128dcddc82704578528d0f609e15c7938f4163b087d577aaf4f127347b3fa0eb336f76cd86097efcc471434323c84490adf93f4b3f24646f9901172563b8404fe6e599b15fc79f242c59d2cc8aebd389c73d462b541a5421fe92c6e7a8ad19d18396d10266c7764cd6704e981d56c96cc06d82f68c06243640d5572284b5f1e2a57ee5fa3a72098905b68f4ff86cdabadf7565f19cc6a95148a0b271e17b1977eac47a11542d68a7497f58c8e6a73ccc7f22dce0ed897429e58c56a0ab28943feed25321d7d2468afcffabd268729afdc782ff994187204249e4fb18b57c2023f25243dffc2bf4e927f317441bd58901457cd870068733b1be37bc56236efdb59e9dfe1607621af2ddf2830978836c523ec2be178d3ccac4e7e40233fa9b8296364454f4a2116e952c9b91372304f690b85b4c98ea4bbe41b55640d0e627e707f1a1a4f0ffe8c87e15d87e965a4e92759ef519b00bdc74890700ed4c42da75329eff93503e638ee0b9b4b37f34f65510af887be7193d9fd3635c238ba27b1ba4437a0e4c82238f81fcda8f7282f356b78eeb6049a43d1aeb25e446a6ea6730d1b5c1eaa0402bb654d703cd36d8d1f4b7e86cad85208a3252c9a47031939a06686f3a8151bdbf64fe0c2fc816e330334407136593b3cac87a1d467f6c5efc86a61622b76a28dac88d4bbc3883ccb8c5dcc6cda38f9e8eee111d5cb9751a2e04c801925c360c7b1be09298b599996e32361570a1066fa8a214dc65d19bf2d62b3f0aa752c2a9325d7d256539f2ba671307fdba19e0679c219101aa6716b3ce99ba5874a306d126efcf175795e75aa547641f2eccf5ca2c427dcb27a56f72629b5bba564032217f3539d854f45c63620094b0c30e25a67bde0452be966643436b364e578456c8fb8b7e7394fd8e0fa1a1ab7115626a062295450f2b4855421b41ae9aa7e969abbb36dd714460c56cd67955f7c453b1abb9a8175a2e419f1e97e1fa971626348a2930d5e28a14b9eef276d569f5b1398d1ac34052dfbe68c00a90fa7d76755daf9dcd44b2c7ad0bec0432368281228935e4f5663cfed92de2eee279b9f5e1143d9b2bbefdf0330e82247b437d9ef6ccf16b15509760b2b2c2c7d2ea48b7c6e9930db5c11aaeaeb2c9868f138c4cd825b2703c6272ed9a1536934d680b858a6db8291919e9f3c03b7f0ee12e8bc4b8ed190d7755cce32a76fb6c28fbcd2813c0ead9343447b3762436581fac0956bfeba9a585aaf88e45207024b3a73a56b7d87544504ad169e89145df2a7718948afe8f024de602a0ce097708de4b5587415c8f8b53f4ea907e0cc4ff09a5212f4a7a13a94351befa7a783581431394f0f11dc007f44d78e4b93527d302410f77646ce28144f26ab790bcff9e8fc6bc13bbd6a1076638b35ee1a2ad9eb56a9c832706ab26f61c9effda50c3dfdb70755e0637d9403780430b105b72d52fb91e2fa96cb125e928cf1d1819ac8b7081bf156b78e7879e61255f91ecf654316ab6e2b4d898cbee10f31b9a8a23896d0d8d90454ccfce73d823d4573bbea880ed17c1e233c25a4334a940f653f1684bbced80dde0deaedd7db8a03ed907071a9d4cb4199509a0f8af5d6169f5e849649b68719e126578bcde94ef84088419ca6c62b994d2a83d7b6ae83a434c45b4bdd33a6e0fd07dc3ca181d7ae19186ce06b166ca3c5eab20c45774c1340c2bc65c8bb005b1c715dd3db9cdddb776ad61865dc7401b6276bee760064fcae83bf8e3cb6d88445a514cb82d67fea5d4d40211425b87cc15e2c21b2e9328f593df9ad1867edbedb90501cb563f4a2d0f3ef20560db1624b1f4fa7776d2040fbfd8a6eca256f4098934f99ee6b219d4feb696d5b69b5267d0494f0dcb1195ece5ca587f253906e0733b7aa830087c3ea293dbe408644288500b387208e74fc4ebfcf08bfd01b0af5bf44ef4462fd73c8aeff752300f746130c9a65c8fabcd1aa8ca6075b748034a3fe36eaa19f0f4f437400598c920233515d496cd5f8ebd805999c75e8aa7a29deb514eadc50e6fe3429d60e481127a06c8c9d6719e636f6644c47cfca6c97a4488ffb93c4a3b139e8122c93b3d5a3c6f2aebc5f3c39a3f8fa061ac4368b635c63510f72238823f61740727d1be2cc4e0c8eaafea8e83356445b3dc58e7cd32542b261ebe880a3dc9f7ac9d3e455485bfbba596bbf3d6cc6d1f32e885acf3d72aa569c80e5a3783c1c97a66e4ced4f99219d85778795e0cefaaa478f8ba313983609b0a788293cee51fe5cf57a725fbc93452381ac8046c140df659e73d96901665c1b2a9a2b150152da3dca803bb11ec42e83a2c77885f05e5bf0473a6ccc3ba2e0901ce45ccdf8a8ba1a37164ac257c81013348f2ef34e49846d60de5d4ba172063b49caffe49822bd4c766f598e74946cbd394b5d12680fd5645e8028b217f3d0a3fa84b7bb78d8ec8bfe1ef76913aafd6b1c57237be153281252b02dfbaf456eaebde69336f9fafb3de04ba35fdae5a598aaf5d901c8b25584e676d674b8907151679d5160c7f2790dac2d0f232e6394ff9cd9bfdb8ff35bc797e7b908dd22dc5929b0387757499b97218f9610e334c5e1a79f7e26441a3e590881f4f63138fa4d3e20e6c3863d62ef9e8e2abecead576df82247ba61b54c2d2bf1b781ec43b9f6c097b99122fd7b95e3ff471f270c22a048165b24a132964c2c8bdc4c3a46c599d9b905cb69f9623dd3c3529a8794b859ae9e49fc4bcf8cbf3cb9b4ff999df26355a0c19dad0891c3af260bf7a979ce6e905180556172ceee81accf85b031e6b10727adb42db266b582749e911250cf0e165b713c8e8871653629991a661ef2770f32c1afae7908581c882393a65653be163f0216800fbed71b5376021acd8170c6b53b4f42db5eeec3110f97a4c4dcc52c173846474a821f1549a698e6541a3ce6ed7db62b8fe8d65f694dcb4cb6b767483a8b49f3966dc2488a3898334095f526456e47eb67a10d9b105767b96fee9c44c12b4fc51c4e0abfe6451530c7409a3f84ea36ea0114036940123fbd50000a23150b7043df22c4a9b08b47dcb1458fc1a8c6a59c19beb019c6852eb2f5cb6e984a57eb6395b75d5f6c2e53d5317b518e59682018f925453843c7876bdf3f5d74c1c6e1abc3793610f6bc60c974d2358ffa101b912913a4afa3b839238b11f78edc99f3da31b31bc181abe99d8b49c6c73978a99f41e20b1da2b95dc316a8b74ec09d8b01b3c7f7c1ec95bf28543d9ecda9104fe0448ed034225d30c5d829ce52836f26661e1971d83c3b4fa86125df73f1210cd232ee0ad3eaca922d2ffd18958412e77082226d45535d68c27b3ca4b545cd86c415c51c0f47301cd4128d8813356bf6c7db483e0870e723c07848cfd6937b8473966edf6ae4c60d39846495aa5e8aaac193e296cddf5a6db3960dc68c6cc2ef04bf29cf727360e1b0d2d86f5a0f809ceb5ae547006b340d31f83eeaddfd1e1a65585a92f00e38418c628580316ee659260a25449a7f9256ab52872f2b3ece03ab2b1d21f87d68bd3a8f7b03df6f861502c46ebb76d10c38aedbb8d21ff7929c254c7b20bf0a114d2ed13c068734bc2cfc351d2dd3fd9107a3d37e65aa22d11982f995fdb453d093552e511cb77ebe43e8f9f5fabf04389a40824156fa1ceb802c2d6c620a8b71eab15214dbee3412aa7d9f193a14b0875c6dd6297c1eced20aa9f1fc1816e19b85b4ad26e5a71c463a58dcdf2bfb85b606540c6013eda834863b6990a1587d807231fa71e9f37be94f4302ce51ddd18486bdf030b2cd521ba1aabfe6b6ce4b387858e6d17c2097a8b0d3e3bb19b2b8712e400afede0f0c2fc7efb7350aaafe02ef78446c35d49c9d924806efe3dd64343eaf007692c6d08c9ad7750fbb79a0fee805e458a4835b91298b33993cfa871dc52fec7bea6532f046308c9c04e1f0683fdf463e2c144c0ec40bf87260ea178a203c1bf1624b092e1e0091cac5729d522e5e548a23a68df02e23920db605bad77dca8517bc841732f79e64e89bf21ed84746bfd643bf2b3b6457caff80c6449e6a8b82244133a9cbaf983b4b1786d05b8f8c11b6801bd7e81b18974626d014d7bf5112ef2ae576eb18000d8cb8828f126f5ed08677cd51ecab72251c5acf4c38055c8e3811b3987f76583431261230d1bab65dfb5723e8d1d565dbd0f001df0f6197b3347b678d718aad6efb0fc6a7bac833fb1b4c1f0148362161ad2353dd53db23a0334341420c57f893ca2ea9cb1094c8f530495d7a5e14eff81913c4c3a94746c0827a28ec63383f71ae5c1d3869d6fb71209982af029bf897332e5662f1dd04e88d54e2e4ae",
        "enc_session_key": "830606cbc4f9401a29c7977d364398a4e3e0b27a7ee2d94263e271b4523bd5f6badcfd8811d50ebb2370847c9a854d84d84008bdbaffaa01a539bc24fb6cf819102a0412eb20d44c13165fea31a49cea13b46df49670327f760a5a1606e42aef93a70ade8acd454ef4b661ae8442033a56dce5b5c29a8747af08523693ff4d226dba48709a7832ab3fb06536a88fb7f80a9ce03c58ea0ad3757864ec5edb0f8a365e078712489ac95f522062d9d7619009bed727d1d4f2c486d53dfd2e27cafce7734c81a190701bc1a556eea2d265d15a9df388c41d979ee57aa9cd25a1ecfc557ae4a31fbd7c7da0e5bc6ece5ceddfc61e73c98ae24b731cf846a0648dc93b"
      },
      "tables": [
        {
          "table_name": "sales_details_test",
          "short_description": "Daily sales with tickets and tickets lines",
          "filename_template": "input_{{FD_DATE}}-{{FD_TIME}}-ORS-ventes.csv",
          "ddl_mode": "file",
          "ddl_file": "ddl/sales_details.json",
          "doc_md": "ddl/sales_details.md",
          "skip_leading_rows": 0,
          "write_disposition": "WRITE_APPEND"
        },
        {
          "table_name": "stores",
          "short_description": "Full Stores referential",
          "filename_template": "input_{{FD_DATE}}-{{FD_TIME}}-ORS-magasins.csv",
          "ddl_mode": "file",
          "ddl_file": "ddl/stores.json",
          "doc_md": "ddl/stores.md"
        }
      ]
    },
  ]
}
```

## 🌐 Global parameters

General information about the data operation

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameter</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>configuration_type</b>
        </p>
        <p>type: string</p>
        <p>mandatory</p>
      </td>
      <td style="text-align:left">Type of data operation.
        <br />
        <br />For an STT data operation, the value is always &quot;storage-to-tables&quot;.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>configuration_id</b>
        </p>
        <p>type: string</p>
        <p>mandatory</p>
      </td>
      <td style="text-align:left">
        <p>ID of the data operation.</p>
        <p>You can pick any name you want, but is has to be <b>unique</b> for this
          data operation type.</p>
        <p>Note that in case of conflict, the newly deployed data operation will
          overwrite the previous one. To guarantee its uniqueness, the best practice
          is to name your data operation by concatenating:</p>
        <ul>
          <li>your account ID,</li>
          <li>the source bucket name,</li>
          <li>and the source directory name.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>environment</b>
        </p>
        <p>type: string</p>
        <p>Mandatory</p>
      </td>
      <td style="text-align:left">Deployment context.
        <br />
        <br />Values: PROD, PREPROD, STAGING, DEV.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>account</b>
        </p>
        <p>type: string</p>
        <p>mandatory</p>
      </td>
      <td style="text-align:left">Your account ID is a 6-digit number assigned to you by your Tailer&#xA0;Platform
        administrator.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>activated</b>
        </p>
        <p>type: boolean</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">Flag used to enable/disable the execution of the data operation.
        <br />
        <br />If not specified, the default value will be &quot;true&quot;.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>archived</b>
        </p>
        <p>type: boolean</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">Flag used to enable/disable the visibility of the data operation&apos;s
        configuration and runs in Tailer&#xA0;Studio.
        <br />
        <br />If not specified, the default value will be &quot;false&quot;.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>short_description</b>
        </p>
        <p>type: string</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">Short description of the context of the configuration.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>doc_md</b>
        </p>
        <p>type: string</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">Path to a file containing a detailed description. The file must be in
        Markdown format.</td>
    </tr>
  </tbody>
</table>

## ⬇ Source parameters \(GCS\)

The destination section contains all information related to the data source provider.

```text
"source": {
  "type": "gcs",
  "gcp_project_id": "fd-io-dlk-orsay",
  "gcs_source_bucket": "mirror-fd-io-exc-demo-wbd--n-in",
  "gcs_source_prefix": "testjul",
  "gcs_archive_prefix": "archive",
  "gcp_credentials_secret": {
    "cipher_aes": "22300825396fabbba6918c292ff3ec1a",
    "tag": "8dd3db4c71bfc2caa8b963d475d1bbd1",
    "ciphertext": "4c74df268d5a7541f8264c2e7a282fd4266ee7783ea7fcb23215db59428bb9bac64742df26afb2c13925c731f24525dff53b751b1363e2a5f5bb0b51d318f63dc3b970b52873a86afae0de8128dcddc82704578528d0f609e15c7938f4163b087d577aaf4f127347b3fa0eb336f76cd86097efcc471434323c84490adf93f4b3f24646f9901172563b8404fe6e599b15fc79f242c59d2cc8aebd389c73d462b541a5421fe92c6e7a8ad19d18396d10266c7764cd6704e981d56c96cc06d82f68c06243640d5572284b5f1e2a57ee5fa3a72098905b68f4ff86cdabadf7565f19cc6a95148a0b271e17b1977eac47a11542d68a7497f58c8e6a73ccc7f22dce0ed897429e58c56a0ab28943feed25321d7d2468afcffabd268729afdc782ff994187204249e4fb18b57c2023f25243dffc2bf4e927f317441bd58901457cd870068733b1be37bc56236efdb59e9dfe1607621af2ddf2830978836c523ec2be178d3ccac4e7e40233fa9b8296364454f4a2116e952c9b91372304f690b85b4c98ea4bbe41b55640d0e627e707f1a1a4f0ffe8c87e15d87e965a4e92759ef519b00bdc74890700ed4c42da75329eff93503e638ee0b9b4b37f34f65510af887be7193d9fd3635c238ba27b1ba4437a0e4c82238f81fcda8f7282f356b78eeb6049a43d1aeb25e446a6ea6730d1b5c1eaa0402bb654d703cd36d8d1f4b7e86cad85208a3252c9a47031939a06686f3a8151bdbf64fe0c2fc816e330334407136593b3cac87a1d467f6c5efc86a61622b76a28dac88d4bbc3883ccb8c5dcc6cda38f9e8eee111d5cb9751a2e04c801925c360c7b1be09298b599996e32361570a1066fa8a214dc65d19bf2d62b3f0aa752c2a9325d7d256539f2ba671307fdba19e0679c219101aa6716b3ce99ba5874a306d126efcf175795e75aa547641f2eccf5ca2c427dcb27a56f72629b5bba564032217f3539d854f45c63620094b0c30e25a67bde0452be966643436b364e578456c8fb8b7e7394fd8e0fa1a1ab7115626a062295450f2b4855421b41ae9aa7e969abbb36dd714460c56cd67955f7c453b1abb9a8175a2e419f1e97e1fa971626348a2930d5e28a14b9eef276d569f5b1398d1ac34052dfbe68c00a90fa7d76755daf9dcd44b2c7ad0bec0432368281228935e4f5663cfed92de2eee279b9f5e1143d9b2bbefdf0330e82247b437d9ef6ccf16b15509760b2b2c2c7d2ea48b7c6e9930db5c11aaeaeb2c9868f138c4cd825b2703c6272ed9a1536934d680b858a6db8291919e9f3c03b7f0ee12e8bc4b8ed190d7755cce32a76fb6c28fbcd2813c0ead9343447b3762436581fac0956bfeba9a585aaf88e45207024b3a73a56b7d87544504ad169e89145df2a7718948afe8f024de602a0ce097708de4b5587415c8f8b53f4ea907e0cc4ff09a5212f4a7a13a94351befa7a783581431394f0f11dc007f44d78e4b93527d302410f77646ce28144f26ab790bcff9e8fc6bc13bbd6a1076638b35ee1a2ad9eb56a9c832706ab26f61c9effda50c3dfdb70755e0637d9403780430b105b72d52fb91e2fa96cb125e928cf1d1819ac8b7081bf156b78e7879e61255f91ecf654316ab6e2b4d898cbee10f31b9a8a23896d0d8d90454ccfce73d823d4573bbea880ed17c1e233c25a4334a940f653f1684bbced80dde0deaedd7db8a03ed907071a9d4cb4199509a0f8af5d6169f5e849649b68719e126578bcde94ef84088419ca6c62b994d2a83d7b6ae83a434c45b4bdd33a6e0fd07dc3ca181d7ae19186ce06b166ca3c5eab20c45774c1340c2bc65c8bb005b1c715dd3db9cdddb776ad61865dc7401b6276bee760064fcae83bf8e3cb6d88445a514cb82d67fea5d4d40211425b87cc15e2c21b2e9328f593df9ad1867edbedb90501cb563f4a2d0f3ef20560db1624b1f4fa7776d2040fbfd8a6eca256f4098934f99ee6b219d4feb696d5b69b5267d0494f0dcb1195ece5ca587f253906e0733b7aa830087c3ea293dbe408644288500b387208e74fc4ebfcf08bfd01b0af5bf44ef4462fd73c8aeff752300f746130c9a65c8fabcd1aa8ca6075b748034a3fe36eaa19f0f4f437400598c920233515d496cd5f8ebd805999c75e8aa7a29deb514eadc50e6fe3429d60e481127a06c8c9d6719e636f6644c47cfca6c97a4488ffb93c4a3b139e8122c93b3d5a3c6f2aebc5f3c39a3f8fa061ac4368b635c63510f72238823f61740727d1be2cc4e0c8eaafea8e83356445b3dc58e7cd32542b261ebe880a3dc9f7ac9d3e455485bfbba596bbf3d6cc6d1f32e885acf3d72aa569c80e5a3783c1c97a66e4ced4f99219d85778795e0cefaaa478f8ba313983609b0a788293cee51fe5cf57a725fbc93452381ac8046c140df659e73d96901665c1b2a9a2b150152da3dca803bb11ec42e83a2c77885f05e5bf0473a6ccc3ba2e0901ce45ccdf8a8ba1a37164ac257c81013348f2ef34e49846d60de5d4ba172063b49caffe49822bd4c766f598e74946cbd394b5d12680fd5645e8028b217f3d0a3fa84b7bb78d8ec8bfe1ef76913aafd6b1c57237be153281252b02dfbaf456eaebde69336f9fafb3de04ba35fdae5a598aaf5d901c8b25584e676d674b8907151679d5160c7f2790dac2d0f232e6394ff9cd9bfdb8ff35bc797e7b908dd22dc5929b0387757499b97218f9610e334c5e1a79f7e26441a3e590881f4f63138fa4d3e20e6c3863d62ef9e8e2abecead576df82247ba61b54c2d2bf1b781ec43b9f6c097b99122fd7b95e3ff471f270c22a048165b24a132964c2c8bdc4c3a46c599d9b905cb69f9623dd3c3529a8794b859ae9e49fc4bcf8cbf3cb9b4ff999df26355a0c19dad0891c3af260bf7a979ce6e905180556172ceee81accf85b031e6b10727adb42db266b582749e911250cf0e165b713c8e8871653629991a661ef2770f32c1afae7908581c882393a65653be163f0216800fbed71b5376021acd8170c6b53b4f42db5eeec3110f97a4c4dcc52c173846474a821f1549a698e6541a3ce6ed7db62b8fe8d65f694dcb4cb6b767483a8b49f3966dc2488a3898334095f526456e47eb67a10d9b105767b96fee9c44c12b4fc51c4e0abfe6451530c7409a3f84ea36ea0114036940123fbd50000a23150b7043df22c4a9b08b47dcb1458fc1a8c6a59c19beb019c6852eb2f5cb6e984a57eb6395b75d5f6c2e53d5317b518e59682018f925453843c7876bdf3f5d74c1c6e1abc3793610f6bc60c974d2358ffa101b912913a4afa3b839238b11f78edc99f3da31b31bc181abe99d8b49c6c73978a99f41e20b1da2b95dc316a8b74ec09d8b01b3c7f7c1ec95bf28543d9ecda9104fe0448ed034225d30c5d829ce52836f26661e1971d83c3b4fa86125df73f1210cd232ee0ad3eaca922d2ffd18958412e77082226d45535d68c27b3ca4b545cd86c415c51c0f47301cd4128d8813356bf6c7db483e0870e723c07848cfd6937b8473966edf6ae4c60d39846495aa5e8aaac193e296cddf5a6db3960dc68c6cc2ef04bf29cf727360e1b0d2d86f5a0f809ceb5ae547006b340d31f83eeaddfd1e1a65585a92f00e38418c628580316ee659260a25449a7f9256ab52872f2b3ece03ab2b1d21f87d68bd3a8f7b03df6f861502c46ebb76d10c38aedbb8d21ff7929c254c7b20bf0a114d2ed13c068734bc2cfc351d2dd3fd9107a3d37e65aa22d11982f995fdb453d093552e511cb77ebe43e8f9f5fabf04389a40824156fa1ceb802c2d6c620a8b71eab15214dbee3412aa7d9f193a14b0875c6dd6297c1eced20aa9f1fc1816e19b85b4ad26e5a71c463a58dcdf2bfb85b606540c6013eda834863b6990a1587d807231fa71e9f37be94f4302ce51ddd18486bdf030b2cd521ba1aabfe6b6ce4b387858e6d17c2097a8b0d3e3bb19b2b8712e400afede0f0c2fc7efb7350aaafe02ef78446c35d49c9d924806efe3dd64343eaf007692c6d08c9ad7750fbb79a0fee805e458a4835b91298b33993cfa871dc52fec7bea6532f046308c9c04e1f0683fdf463e2c144c0ec40bf87260ea178a203c1bf1624b092e1e0091cac5729d522e5e548a23a68df02e23920db605bad77dca8517bc841732f79e64e89bf21ed84746bfd643bf2b3b6457caff80c6449e6a8b82244133a9cbaf983b4b1786d05b8f8c11b6801bd7e81b18974626d014d7bf5112ef2ae576eb18000d8cb8828f126f5ed08677cd51ecab72251c5acf4c38055c8e3811b3987f76583431261230d1bab65dfb5723e8d1d565dbd0f001df0f6197b3347b678d718aad6efb0fc6a7bac833fb1b4c1f0148362161ad2353dd53db23a0334341420c57f893ca2ea9cb1094c8f530495d7a5e14eff81913c4c3a94746c0827a28ec63383f71ae5c1d3869d6fb71209982af029bf897332e5662f1dd04e88d54e2e4ae",
    "enc_session_key": "830606cbc4f9401a29c7977d364398a4e3e0b27a7ee2d94263e271b4523bd5f6badcfd8811d50ebb2370847c9a854d84d84008bdbaffaa01a539bc24fb6cf819102a0412eb20d44c13165fea31a49cea13b46df49670327f760a5a1606e42aef93a70ade8acd454ef4b661ae8442033a56dce5b5c29a8747af08523693ff4d226dba48709a7832ab3fb06536a88fb7f80a9ce03c58ea0ad3757864ec5edb0f8a365e078712489ac95f522062d9d7619009bed727d1d4f2c486d53dfd2e27cafce7734c81a190701bc1a556eea2d265d15a9df388c41d979ee57aa9cd25a1ecfc557ae4a31fbd7c7da0e5bc6ece5ceddfc61e73c98ae24b731cf846a0648dc93b"
  }
}
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameter</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>type</b>
        </p>
        <p>type: string</p>
        <p>mandatory</p>
      </td>
      <td style="text-align:left">
        <p>Source type.</p>
        <p>The only supported source type for now is &quot;gcs&quot;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>gcp_project_id</b>
        </p>
        <p>type: string</p>
        <p>mandatory</p>
      </td>
      <td style="text-align:left">
        <p>Specify the Google Cloud Platform project where to deploy the data operation
          and its associated cloud functions.</p>
        <p>If not set, the user will be prompted to choose a project.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>gcs_source_bucket</b>
        </p>
        <p>type: string</p>
        <p>mandatory</p>
      </td>
      <td style="text-align:left">Name of the source bucket.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>gcs_source_prefix</b>
        </p>
        <p>type: string</p>
        <p>mandatory</p>
      </td>
      <td style="text-align:left">Path where the files will be found, e.g. &quot;some/sub/dir&quot;.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>gcs_archive_prefix</b>
        </p>
        <p>type: string optional</p>
      </td>
      <td style="text-align:left">
        <p>Path where the source files will be archived.</p>
        <p>If present and populated, the STT data operation will archive the source
          files in the location specified, in the GCS source bucket.</p>
        <p>If not present or empty, there will be no archiving.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>gcp_credentials_secret</b>
        </p>
        <p>type: dict</p>
        <p>mandatory</p>
      </td>
      <td style="text-align:left">
        <p>Encrypted credentials needed to read/move data from the source bucket.</p>
        <p>You should have generated credentials when <a href="../../getting-started/set-up-google-cloud-platform.md">setting up GCP</a>.
          To learn how to encrypt them, refer to <a href="../../getting-started/encrypt-your-credentials.md">this page</a>.</p>
      </td>
    </tr>
  </tbody>
</table>

## ⬆ Destination parameters \(BigQuery\)

The destination section contains all the information related to the data destinations.

The **destinations** parameter is an array containing maps. Each map can contain a type of destination and many actual "tables" as ultimate destination.

Example:

```text
"destinations": [
{
  "type": "bigquery",
  "gcp_project_id": "fd-io-dlk-orsay",
  "gbq_dataset": "dlk_demo_wbd_psa",
  "source_format": "CSV",
  "create_disposition": "CREATE_IF_NEEDED",
  "write_disposition": "WRITE_TRUNCATE",
  "skip_leading_rows": 1,
  "field_delimiter": "|",
  "gcp_credentials_secret": {
    "cipher_aes": "223008256918c292ff3ec1a",
    "tag": "8dd3db4c71bfb963d475d1bbd1",
    "ciphertext": "4c74df268d5a7541f8264c2e7a282f",
    "enc_session_key": "830606cbc4f9401a29c7977d364398"
    },
      "tables": [
      {
        "table_name": "sales_details_test",
        "short_description": "Daily detailed Sales with tickets and tickets lines",
        "filename_template": "input_{{FD_DATE}}-{{FD_TIME}}-ORS-ventes.csv",
        "ddl_mode": "file",
        "ddl_file": "ddl/sales_details.json",
        "doc_md": "ddl/sales_details.md",
        "skip_leading_rows": 0,
        "write_disposition": "WRITE_APPEND"
      },
      {
        "table_name": "stores",
        "short_description": "Full Stores referential",
        "filename_template": "input_{{FD_DATE}}-{{FD_TIME}}-ORS-magasins.csv",
        "ddl_mode": "file",
        "ddl_file": "ddl/stores.json",
        "doc_md": "ddl/stores.md"
      }
    ]
  }
]
```

### Global destination parameters

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameter</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>type</b>
        </p>
        <p>type: string</p>
        <p>mandatory</p>
      </td>
      <td style="text-align:left">
        <p>Type of destination.</p>
        <p>The only supported destination type for now is &quot;bigquery&quot;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>gcp_project_id</b>
        </p>
        <p>type: string</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">
        <p>Default GCP Project ID.
          <br />Default value: None</p>
        <p>This parameter can be set for each <b>table</b> sub-object, and will be
          overridden by that value if it is different.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>gbq_dataset</b>
        </p>
        <p>type: string</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">
        <p>Default value: None</p>
        <p>This parameter can be set for each <b>table</b> sub-object, and will be
          overridden by that value if it is different.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>gcp_credentials_secret</b>
        </p>
        <p>type: object</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">
        <p>Encrypted credentials needed to interact with Storage and BigQuery.</p>
        <p>You should have generated credentials when <a href="../../getting-started/set-up-google-cloud-platform.md">setting up GCP</a>.
          To learn how to encrypt them, refer to <a href="../../getting-started/encrypt-your-credentials.md">this page</a>.</p>
        <p>Default value: None</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>source_format</b>
        </p>
        <p>type: string</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">
        <p>Default source format for input files.</p>
        <p>Possible values (case sensitive):</p>
        <ul>
          <li>&quot;CSV&quot; (default)</li>
          <li>&quot;JSON&quot;</li>
        </ul>
        <p>This parameter can be set for each <b>table</b> sub-object, and will be
          overridden by that value if it is different.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>create_disposition</b>
        </p>
        <p>type: string</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">
        <p>Specifies behavior for creating tables (see <a href="https://googleapis.github.io/google-cloud-python/latest/bigquery/generated/google.cloud.bigquery.job.CreateDisposition.html#google.cloud.bigquery.job.CreateDisposition">Google BigQuery documentation</a>).</p>
        <p>Possible values:</p>
        <ul>
          <li>&quot;CREATE_IF_NEEDED&quot; (default): If the table does not exist, BigQuery
            creates the table.</li>
          <li>&quot;CREATE_NEVER&quot;: The table must already exist.</li>
        </ul>
        <p>This parameter can be set for each <b>table</b> sub-object, and will be
          overridden by that value if it is different.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>write_disposition</b>
        </p>
        <p>type: string</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">
        <p>Action that occurs if the destination table already exists (see <a href="https://googleapis.github.io/google-cloud-python/latest/bigquery/generated/google.cloud.bigquery.job.WriteDisposition.html#google.cloud.bigquery.job.WriteDisposition">Google BigQuery documentation</a>).</p>
        <p>Possible values:</p>
        <ul>
          <li>&quot;WRITE_TRUNCATE&quot; (default): The run will write table data from
            the beginning. If the table already contained lines, they will all be deleted
            and replaced by the new lines. This option is used most of the time for
            daily runs to avoid duplicates.</li>
          <li>&quot;WRITE_APPEND&quot;: The run will append new lines to the table.
            When using this option, make sure not to run the data operation several
            times.</li>
          <li>&quot;WRITE_EMPTY&quot;: This option only allows adding data to an empty
            table. If the table already contains data, it returns an error. It is hardly
            ever used as data operations are usually run periodically, so they will
            always contain data after the first run.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>skip_leading_rows</b>
        </p>
        <p>type: integer</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">
        <p>Number of rows to skip when reading data, CSV only.</p>
        <p>Default value: 1</p>
        <p>This parameter can be set for each <b>table</b> sub-object, and will be
          overridden by that value if it is different.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>field_delimiter</b>
        </p>
        <p>type: string</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">
        <p>Separator for fields in a CSV file, e.g. &quot;;&quot;.</p>
        <p><b>Note</b>: For Tab separator, set to &quot;\t&quot;.</p>
        <p>Default value: &quot;|&quot;</p>
        <p>This parameter can be set for each <b>table</b> sub-object, and will be
          overridden by that value if it is different.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>quote_character</b>
        </p>
        <p>type: string</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">
        <p>Character used to quote data sections, CSV only (see <a href="https://googleapis.dev/python/bigquery/latest/generated/google.cloud.bigquery.job.LoadJobConfig.html#google.cloud.bigquery.job.LoadJobConfig.quote_character">Google BigQuery documentation</a>).</p>
        <p>Default value: &quot;&quot;</p>
        <p>This parameter can be set for each <b>table</b> sub-object, and will be
          overridden by that value if it is different.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>null_marker</b>
        </p>
        <p>type: string</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">
        <p>Represents a null value, CSV only (see <a href="https://googleapis.dev/python/bigquery/latest/generated/google.cloud.bigquery.job.LoadJobConfig.html#google.cloud.bigquery.job.LoadJobConfig.null_marker">Google BigQuery documentation</a>).</p>
        <p>Default value: &quot;&quot;</p>
        <p>This parameter can be set for each <b>table</b> sub-object, and will be
          overridden by that value if it is different.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>bq_load_job_ignore_unknown_values</b>
        </p>
        <p>type: boolean</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">
        <p>Ignore extra values not represented in the table schema (see <a href="https://googleapis.dev/python/bigquery/latest/generated/google.cloud.bigquery.job.LoadJobConfig.html#google.cloud.bigquery.job.LoadJobConfig.ignore_unknown_values">Google BigQuery documentation</a>).</p>
        <p>Default value: false</p>
        <p>This parameter can be set for each <b>table</b> sub-object, and will be
          overridden by that value if it is different.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>bq_load_job_max_bad_records</b>
        </p>
        <p>type: integer</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">
        <p>Number of invalid rows to ignore (see <a href="https://googleapis.dev/python/bigquery/latest/generated/google.cloud.bigquery.job.LoadJobConfig.html#google.cloud.bigquery.job.LoadJobConfig.max_bad_records">Google BigQuery documentation</a>).</p>
        <p>Default value: 0</p>
        <p>This parameter can be set for each <b>table</b> sub-object, and will be
          overridden by that value if it is different.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>bq_load_job_schema_update_options</b>
        </p>
        <p>type: array</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">
        <p>Specifies updates to the destination table schema to allow as a side effect
          of the load job (see <a href="https://googleapis.dev/python/bigquery/latest/generated/google.cloud.bigquery.job.LoadJobConfig.html#google.cloud.bigquery.job.LoadJobConfig.max_bad_records">Google BigQuery documentation</a>).</p>
        <p>Default value: []</p>
        <p>This parameter can be set for each <b>table</b> sub-object, and will be
          overridden by that value if it is different.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>bq_load_job_allow_quoted_newlines</b>
        </p>
        <p>type: boolean</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">
        <p>Allows quoted data containing newline characters, CSV only (see <a href="https://googleapis.dev/python/bigquery/latest/generated/google.cloud.bigquery.job.LoadJobConfig.html#google.cloud.bigquery.job.LoadJobConfig.max_bad_records">Google BigQuery documentation</a>).</p>
        <p>Default value: false</p>
        <p>This parameter can be set for each <b>table</b> sub-object, and will be
          overridden by that value if it is different.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>bq_load_job_allow_jagged_rows</b>
        </p>
        <p>type : boolean</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">
        <p>Allows missing trailing optional columns, CSV only (see <a href="https://googleapis.dev/python/bigquery/latest/generated/google.cloud.bigquery.job.LoadJobConfig.html#google.cloud.bigquery.job.LoadJobConfig.max_bad_records">Google BigQuery documentation</a>).</p>
        <p>Default value: false</p>
        <p>This parameter can be set for each <b>table</b> sub-object, and will be
          overridden by that value if it is different.</p>
      </td>
    </tr>
  </tbody>
</table>

### **Table sub-object parameters**

The "table" object contains the definition of expected input files and their BigQuery target.

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Parameter</b>
      </th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>table_name</b>
        </p>
        <p>type: string</p>
        <p>mandatory</p>
      </td>
      <td style="text-align:left">Name of the destination BigQuery table.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>short_description</b>
        </p>
        <p>type: string</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">Short description of the destination BigQuery table.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>filename_template</b>
        </p>
        <p>type: string</p>
        <p>mandatory</p>
      </td>
      <td style="text-align:left">
        <p>Template for the files to be processed.
          <br />The following placeholders are currently supported:</p>
        <ul>
          <li>&quot;FD_DATE&quot; looks for an 8-digit date (e.g. &quot;20191015&quot;).</li>
          <li>&quot;FD_TIME&quot; looks for a 6-digit time (e.g. &quot;124213&quot;).</li>
          <li>&quot;FD_BLOB_n&quot;, where &quot;n&quot; is a non-zero positive integer,
            looks for a string of characters of &quot;n&quot; length.</li>
          <li>FD_TABLE_NAME: This is a special template used when you have to process
            a large number of different files sharing the same destination schema.
            This template has to be used in conjunction with the <b>table_name</b> parameter.</li>
        </ul>
        <p><b>Example 1</b>
        </p>
        <p>This template:</p>
        <p><code>&quot;stores_{{FD_DATE}}_{{FD_TIME}}.txt&quot;</code>
        </p>
        <p>will allow you to process this type of files:</p>
        <p>&quot;stores_20201116_124213.txt&quot;</p>
        <p></p>
        <p><b>Example 2</b>
        </p>
        <p>This template:</p>
        <p><code>&quot;{{FD_DATE}}_{{FD_BLOB_5}}_fixedvalue_{{FD_BLOB_11}}.gz&quot;</code>
        </p>
        <p>will allow you to process this type of files:</p>
        <p>&quot;20201116_12397_fixedvalue_12312378934.gz&quot;</p>
        <p></p>
        <p><b>Example 3</b>
        </p>
        <p>If <b>table_name</b> is set to: <code>&quot;table_{{FD_TABLE_NAME}}&quot;</code>
        </p>
        <p>and <b>filename_template</b> to: <code>&quot;{{FD_DATE}}_{{FD_TIME}}_fixedvalue_{{FD_TABLE_NAME}}.csv&quot;</code>
        </p>
        <p>A file named &quot;20201116_124523_fixedvalue_stores.csv&quot; will be
          loaded into a table named: &quot;table_stores_20191205&quot;</p>
        <p>A file named &quot;20190212_063412_fixedvalue_visits.csv&quot; will be
          loaded into a table named: &quot;table_visits_20190212&quot;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>ddl_mode</b>
        </p>
        <p>type: string</p>
        <p>mandatory</p>
      </td>
      <td style="text-align:left">
        <p>This parameter allows you to specify how the schema of the table will
          be obtained.</p>
        <p></p>
        <p>Possible values:</p>
        <ul>
          <li>&quot;file&quot;: Legacy mode. The table schema is described in the DDL
            file specified in the <b>ddl_file</b> parameter.</li>
          <li>&quot; file_template&quot;: The table schema is described in a DDL file
            provided in the source directory together with the source file. It must
            have the same filename as the source file, with the &quot;.ddl.json&quot;
            suffix.</li>
          <li>&quot;header&quot; (CSV file only): The columns of the CSV file first
            line are automatically used as columns for the database table. All the
            columns are given the STRING type. No DDL file needs to be provided.</li>
          <li>&quot;autodetect&quot; (not recommended): Google&#x2019;s default mode.
            The schema is automatically detected from the source file. This mode doesn&#x2019;t
            work well with CSV files, but gives good results with structured formats
            such as JSON. (see <a href="https://cloud.google.com/bigquery/docs/schema-detect">Google BigQuery documentation</a>).</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>ddl_file</b>
        </p>
        <p>type: string</p>
        <p>mandatory if <b>ddl_mode</b> is set to &quot;file&quot;</p>
      </td>
      <td style="text-align:left">Path to the <a href="storage-to-tables-ddl-files.md">DDL file</a> where
        the destination schema is described.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>doc_md<br /></b>type: string
        <br />optional</td>
      <td style="text-align:left">Path to the Markdown file containing detailed information about the destination
        table.</td>
    </tr>
  </tbody>
</table>

