---
title: Настройка клиентского опыта Mac в Skype для бизнеса
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.reviewer: PhillipGarding
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d1d9cfec-e923-4d02-a306-ee40a9114cb8
description: В этой статье описываются клиентские предпочтения и по умолчанию, доступные для Skype для бизнеса mac-клиента, а также то, как их редактировать из-за пределов приложения.
ms.openlocfilehash: 909756b25f9ad3ee17536f24a4143b5b72180918
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838351"
---
# <a name="customize-the-mac-client-experience-in-skype-for-business"></a>Настройка клиентского опыта Mac в Skype для бизнеса
 
В этой статье описываются клиентские предпочтения и по умолчанию, доступные для Skype для бизнеса mac-клиента, а также то, как их редактировать из-за пределов приложения.
  
## <a name="skype-for-business-on-mac-client-preference-settings"></a>Skype для бизнеса параметров предпочтений клиентов Mac

Некоторые функции и поведение, доступные Skype для бизнеса для клиентов Mac, определяются настройками предпочтений клиента. Параметры Skype для бизнеса на Mac находятся в файле, расположенном на macs, которые установили Skype для бизнеса клиента, расположенного по следующему пути: 
  
 **~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**
  
Чтобы задать эти параметры, перейдите к подсказке терминала на Mac клиента и по мере необходимости введите по умолчанию пишите ключевые команды com.microsoft.SkypeForBusiness с помощью ключей предпочтений, описанных в следующей таблице.
  
**Ключи предпочтений клиента**


| Key | Тип | Значение | Описание |
|:-----|:-----|:-----|:-----|
|autoDetectAutoDicoveryURLs    |Логический    |0 = ручная конфигурация сервера  <br/> 1 = автоматическое обнаружение сервера (по умолчанию)    |Укажите, Skype для бизнеса определяет транспорт и сервер для использования во время входной записи. Если вы включаете этот параметр политики, необходимо указать **internalAutoDiscoveryURL** и **externalAutoDiscoveryURL**.   |
|internalAutoDiscoveryURL    |Строка    |Полный URL-адрес автооткрытия    |ВНУТРЕННИЙ URL-адрес автооткрытия    |
|externalAutoDiscoveryURL    |Строка    |Полный URL-адрес автооткрытия    |Внешний URL-адрес автооткрытия    |
|httpProxyDomain    |Строка    ||Домен HTTP Прокси    |
|httpProxyUserName    |Строка    ||ИМЯ пользователя HTTP Прокси    |
|httpProxyPassword    |Строка    ||Пароль прокси-сервера HTTP    |
|trustedDomainList    |Массив    ||Список доверенных доменов для перенаправлений HTTP.    |
|autoAcceptTimeout    |Число    |300 (по умолчанию)    |Автоматическое принятие времени для пользователей без истории беседы на стороне сервера.    |
|warnWhenUnknownLocationForE911    |Логический    |0 = Отключено  <br/> 1 = Включено    |Предупреждает пользователя при наборе экстренного номера из неизвестного расположения.    |
|sipAddress    |Строка    ||SIP-адрес (электронная почта), используемый для регистрации Skype для бизнеса.    |
|userName    |String    ||UpN (UserName), используемый для регистрации для Skype для бизнеса.    |
|userNameInAdvancedOnly    |Логический    |0 = отображение поля Имя пользователя на главном экране входной записи и в диалоговом окне Advanced Properties  <br/> 1 = отображение поля Имя пользователя только в диалоговом окне Advanced Properties (по умолчанию)    |Укажите, где отображается поле Имя пользователя при входе.    |
   
### <a name="usage-examples"></a>Примеры использования

Чтобы добавить один домен (Contoso.com) в список доверенных доменов, необходимо использовать ключ trustedDomainList, как показано:
  
по умолчанию пишут com.microsoft.SkypeForBusiness trustedDomainList -array-add "Contoso.com"
  
Чтобы добавить несколько доменов в надежный список доменов, необходимо использовать ключ trustedDomainList, как показано:
  
по умолчанию пишут com.microsoft.SkypeForBusiness trustedDomainList -array-add "sfb.com" "abc.com" "test.org"
  
### <a name="sample-unedited-settings"></a>Пример неоконченных параметров

Для справки, вот пример файла параметров с использованием только параметров по умолчанию: 
  
```console
{
    BITApplicationDidEnterBackgroundTime = "1496164840.505589";
    BITApplicationWasLaunched = 1;
    CallHistorySelectedFilterIndex = 0;
    HockeySDKAutomaticallySendCrashReports = 0;
    HockeySDKCrashReportActivated = 1;
    "LastSignOut_me" = "2017-05-30 17:22:17 +0000";
    "NSSplitView Subview Frames CallHistoryListDetailSplit" =     (
        "0.000000, 0.000000, 291.500000, 473.000000, NO, NO",
        "292.500000, 0.000000, 408.500000, 473.000000, NO, NO"
    );
    "NSSplitView Subview Frames calendarListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
   "NSSplitView Subview Frames conversationListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
    "NSWindow Frame HomeWindow" = "511 134 769 473 0 0 1280 778 ";
    "NSWindow Frame SignInWindow" = "388 208 512 518 0 0 1280 778 ";
    RawCameraSupportVersion = 7030;
    appRunning = 1;
    buildTime = "May 22 2017 12:37:28";
    "user@contoso.com_userPreferences" =     {
        ContactsListState =         {
            expandedGroupState =             {
                "/me/pendingContacts" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/HR6ZQDk_JUI9WUR0Gq0TEAUYfYDk8OwzsPAuDxZfjxg=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/N-kLDW4VAs4O3PDv36MNyaYxhuqkRGD1eWpzDGdaHnw=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/RJk1X9SsFDq-MbvPe2eUyKTdPizt7-eMxij-ef1SGWQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/UulRAGZQL3JnSpYCDqy4KsZCboNF2pqmp-ru3sqiDPQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/Wsbhk9lfd8OUv_0aCtHmYPfm0Wal0mzoM5WFbkxaNjM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/afYHfnLUqTmnwac55OaqHUNqLLCqFTZuDezsBeSLOko=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/aok8RuCx35GbuVLMp-_Zi4gnBK_c5qO7mANf4Drf8Ak=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/hSrWaq6LWhzvT6sRxpyQimwfXzMgLyEc3O4FgSokesc=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/mDdgSHulTTkweoDbjXVp7Y308xM70eFDDZn2j7sAytM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/nj3ApLemRK23ChI-K3x_RRGjlEeqTh6_9w6kYwKWldQ=" = 1;
                "/ucwa/v1/applications/414177012058/people/groups/oRX0pDJ2zEP-DQOfynLdvnTEFFNnsv95uvCmVfHjSik=" = 0;
            };
        };
    };
    defaultAudioPlaybackDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    defaultAudioRecordingDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    firstRun = 0;
    showEndCallDialog = 1;
}
```
