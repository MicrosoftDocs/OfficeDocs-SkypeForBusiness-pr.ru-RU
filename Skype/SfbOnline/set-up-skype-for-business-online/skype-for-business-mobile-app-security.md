---
title: Безопасность мобильного приложения Skype для бизнеса
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'Узнайте, как настроить безопасность мобильных приложений для пользователей. '
ms.openlocfilehash: d599542970cec5aa4206f29d3ff7fa27ce36e9a0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109955"
---
# <a name="skype-for-business-mobile-app-security"></a>Безопасность мобильного приложения Skype для бизнеса

## <a name="skype-for-business-client-security"></a>Безопасность клиентов Skype для бизнеса

В этой статье описывается информация о шифровании данных в мобильных приложениях Skype для бизнеса.
  
|||||
|:-----|:-----|:-----|:-----|
||**Имя пользователя/пароль** <br/> |**Данные приложений (беседы, <br/> список контактов, собрания)** <br/> |**Журналы диагностики** <br/> |
|**Android** <br/> |Учетные данные хранятся в учетных записях Android. Кроме того, мы шифруем учетные данные, прежде чем сохранять их в учетных записях. Для шифрования используется алгоритм **"AES/CBC/PKCS5Padding".** <br/> |Мы храним в зашифрованной SQL с помощью библиотеки [sqlcipher.](https://www.zetetic.net/sqlcipher/design/) В режиме CBC используется алгоритм 256-битной версии AES по умолчанию. Хранимые данные всегда шифруются в файле базы данных и расшифровываются только при переходе в переменную память и стопки вызовов приложения. Кроме того, файлы голосовой почты шифруются таким же образом, как имя пользователя и пароль (они не хранятся в службе DB). Для воспроизведения голосовая почта временно расшифрована на диске.  <br/> |Эта информация не шифруется.  <br/> |
|**iOS** <br/> |Мы НЕ шифруем имя пользователя и пароль вchain. Однако сама по себе будет зашифрована.  <br/> |Мы уже используем флаг защиты данных [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) для всех файлов в хранилище приложений. Это означает, что файлы в хранилище приложений шифруются до тех пор, пока пользователь не разблокирует устройство в первый раз после перезагрузки устройства. <br/> |Эта информация не шифруется.  <br/> |
|**Windows Phone** <br/> |Windows Phone использует DPAPI (Data Protection API) в Windows для защиты паролей. По нашему мнению, используется схема шифрования AES. В Windows нет возможности настроить размер ключа (или схему), поэтому это то, что предоставляет DPAPI. Оно использует устройство TPM для обеспечения безопасности ключей, определенных для пользователя и устройства. Обратите внимание, что ключи DPAPI не специфичены для приложения.  <br/> |Данные приложения WP защищены с помощью [DPAP](/previous-versions/windows/apps/hh487164(v=vs.105))I, как и creds. В зависимости от нужного уровня детализации некоторые сведения об индексе для данных приложения защищаются с помощью шифрования AES (не DPAPI), что позволяет избежать разолтания, чтобы мы могли искать данные без расшифровки, а ключ, в свою очередь, защищен DPAPI. Кэшные данные могут быть прочитано любым процессом с того же телефона, предполагается, что они могут попасть в папку данных. Шифрование Windows не защищает от взлома в песочнице, только попытки внешнего доступа.  <br/> |Эта информация не шифруется.  <br/> |
   
**Примечание.** Чтобы ознакомиться с [этой открытой документацией](/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) по закреплению устройств на всех платформах Mobile выше, обратитесь к этой документации.
  
## <a name="related-topics"></a>Статьи по теме
[Настройка Skype для бизнеса Online](set-up-skype-for-business-online.md)

[Разрешение на добавление контактов Skype пользователям Skype для бизнеса](let-skype-for-business-users-add-skype-contacts.md)

  
