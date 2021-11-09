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
ms.openlocfilehash: cc077feeb8c7c832f0bfdaea87620b77d914bf95
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863106"
---
# <a name="skype-for-business-mobile-app-security"></a>Безопасность мобильного приложения Skype для бизнеса

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

## <a name="skype-for-business-client-security"></a>Skype для бизнеса Безопасность клиента

В этой статье описывается информация о шифровании данных в Skype для бизнеса мобильных приложениях.
  
||**Имя пользователя/пароль** <br/> |**Данные приложений (беседы, <br/> список контактов, собрания)** <br/> |**Журналы диагностики** <br/> |
|:-----|:-----|:-----|:-----|
|**Android** <br/> |Учетные данные хранятся в учетных записях Android. Кроме того, мы шифруем учетные данные, прежде чем сохранять их в учетных записях. Для шифрования используется алгоритм **AES/CBC/PKCS5Padding** " . <br/> |Мы храним в зашифрованной SQL с помощью библиотеки [sqlcipher.](https://www.zetetic.net/sqlcipher/design/) Мы используем алгоритм 256-битной версии AES по умолчанию в режиме CBC. Хранимые данные всегда шифруются в файле базы данных и расшифровываются только при переходе между нестабильной памятью и стопкой вызовов приложения. Файлы голосовой почты шифруются так же, как имя пользователя и шифрование паролей (они[/mem/intune/protect/device-compliance-get-started](/mem/intune/protect/device-compliance-get-started) не хранятся в DB). Голосовая почта временно расшифрована на диске, чтобы разрешить воспроизведение.  <br/> |Эта информация не шифруется.  <br/> |
|**iOS** <br/> |Мы НЕ шифруем имя пользователя и пароль в пакете ключей. Однако сама по себе шифруется.  <br/> |Мы уже используем [флаг защиты данных NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) для всех файлов в хранилище приложений. Это означает, что файлы в хранилище приложений шифруются до тех пор, пока пользователь не разблокирует устройство в первый раз после перезагрузки устройства. <br/> |Эта информация не шифруется.  <br/> |
|**Windows Phone** <br/> |Windows Phone для защиты паролей используется API DPAPI (Data Protection API) в Windows. Я считаю, что используется схема шифрования AES. Windows не дает возможность настроить размер ключа (или схему), поэтому это то, что дает DPAPI. Оно будет использовать TPM устройства для защиты ключей, которые являются специфическими для пользователя и устройства. Обратите внимание, что ключи DPAPI не специфичены для приложения.  <br/> |Данные приложения WP защищены с помощью [DPAP](/previous-versions/windows/apps/hh487164(v=vs.105))I, как и creds. В зависимости от уровня детализации некоторые сведения об индексе для данных приложения защищаются с помощью шифрования AES (не DPAPI), чтобы избежать засоленности, поэтому мы можем искать данные без расшифровки, и этот ключ, в свою очередь, защищен DPAPI. Кэшные данные могут быть считываемы любым процессом на том же телефоне, предполагается, что они могут попасть в нашу папку данных. Windows шифрование не защищает от взлома в песочнице, а только попытки внешнего доступа.  <br/> |Эта информация не шифруется.  <br/> |
   
**Примечание.** Обратитесь к [этой открытой документации по](/mem/intune/protect/device-compliance-get-started) закреплению устройств, которые доступны на каждой из вышеперечисленных платформ Для мобильных устройств.
  
## <a name="related-topics"></a>Статьи по теме
[Настройка Skype для бизнеса Online](set-up-skype-for-business-online.md)

[Разрешение на добавление контактов Skype пользователям Skype для бизнеса](let-skype-for-business-users-add-skype-contacts.md)

  
