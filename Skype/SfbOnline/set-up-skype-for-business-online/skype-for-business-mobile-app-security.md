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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'Узнайте, как настроить безопасность мобильных приложений для пользователей. '
ms.openlocfilehash: 91c95b1840e8b9e8777a7b1adebf32889910b48c
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013803"
---
# <a name="skype-for-business-mobile-app-security"></a>Безопасность мобильного приложения Skype для бизнеса

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

## <a name="skype-for-business-client-security"></a>Безопасность клиента Skype для бизнеса

В этой статье описывается информация о шифровании данных в мобильных приложениях Skype для бизнеса.
  
||**Имя пользователя/пароль** <br/> |**Данные приложений (беседы, <br/> список контактов, собрания)** <br/> |**Журналы диагностики** <br/> |
|:-----|:-----|:-----|:-----|
|**Android** <br/> |Учетные данные хранятся в учетных записях Android. Кроме того, мы шифруем учетные данные, прежде чем сохранять их в учетных записях. Для шифрования используется алгоритм **AES/CBC/PKCS5Padding** " . <br/> |Зашифрованная база данных SQL хранится в библиотеке [sqlcipher.](https://www.zetetic.net/sqlcipher/design/) Мы используем алгоритм 256-битной версии AES по умолчанию в режиме CBC. Хранимые данные всегда шифруются в файле базы данных и расшифровываются только при переходе между переменной памятью и стопкой вызовов приложения. Файлы голосовой почты шифруются таким же способом, что и имя пользователя и шифрование паролей (они не хранятся [https://docs.microsoft.com/en-us/mem/intune/protect/device-compliance-get-started](/mem/intune/protect/device-compliance-get-started) в DB). Voicemails are temporarily unencrypted on disk to allow playback.  <br/> |Эта информация не шифруется.  <br/> |
|**iOS** <br/> |Мы НЕ шифруем имя пользователя и пароль в пакете ключей. Однако сама по себе шифруется.  <br/> |Мы уже используем [флаг защиты данных NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) для всех файлов в хранилище приложений. Это означает, что файлы в хранилище приложений шифруются до тех пор, пока пользователь не разблокирует устройство в первый раз после перезагрузки устройства. <br/> |Эта информация не шифруется.  <br/> |
|**Windows Phone** <br/> |Windows Phone использует API DPAPI (Data Protection API) в Windows для защиты паролей. Я считаю, что используется схема шифрования AES. В Windows нет возможности настроить размер ключа (или схему), поэтому это то, что дает DPAPI. Оно будет использовать TPM устройства для защиты ключей, которые являются специфическими для пользователя и устройства. Обратите внимание, что ключи DPAPI не специфичены для приложения.  <br/> |Данные приложения WP защищены с помощью [DPAP](/previous-versions/windows/apps/hh487164(v=vs.105))I, как и creds. В зависимости от уровня детализации некоторые сведения об индексе для данных приложения защищаются с помощью шифрования AES (не DPAPI), чтобы избежать засоленности, поэтому мы можем искать данные без расшифровки, и этот ключ, в свою очередь, защищен DPAPI. Кэшные данные могут быть считываемы любым процессом на том же телефоне, предполагается, что они могут попасть в нашу папку данных. Шифрование Windows не защищает от нарушения безопасности в песочнице, а только попытки внешнего доступа.  <br/> |Эта информация не шифруется.  <br/> |
   
**Примечание.** Обратитесь к [этой открытой документации по](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started) закреплению устройств на всех платформах, которые доступны на каждой из вышеперечисленных платформ.
  
## <a name="related-topics"></a>Статьи по теме
[Настройка Skype для бизнеса Online](set-up-skype-for-business-online.md)

[Разрешение на добавление контактов Skype пользователям Skype для бизнеса](let-skype-for-business-users-add-skype-contacts.md)

  
