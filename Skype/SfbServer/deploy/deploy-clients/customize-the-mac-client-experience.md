---
title: Настройка клиентского опыта Mac в Skype для бизнеса
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: PhillipGarding
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d1d9cfec-e923-4d02-a306-ee40a9114cb8
description: В этой статье описаны параметры клиента и параметры по умолчанию, доступные для клиента Skype для бизнеса на Mac, а также их редактирование из-за пределов приложения.
ms.openlocfilehash: cdbd1c109fffddf6d922657285f60d9b4f06924a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805759"
---
# <a name="customize-the-mac-client-experience-in-skype-for-business"></a>Настройка клиентского опыта Mac в Skype для бизнеса
 
В этой статье описаны параметры клиента и параметры по умолчанию, доступные для клиента Skype для бизнеса на Mac, а также их редактирование из-за пределов приложения.
  
## <a name="skype-for-business-on-mac-client-preference-settings"></a>Параметры параметров клиента Skype для бизнеса на Mac

Некоторые функции и поведение, доступные клиентам Skype для бизнеса на Mac, определяются настройками параметров клиента. Параметры Skype для бизнеса на Mac находятся в файле, расположенном на компьютере Mac с установленным клиентом Skype для бизнеса, расположенным по следующему пути: 
  
 **~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**
  
Чтобы настроить эти параметры, перейдите к запросу терминала на компьютере Mac клиента и при необходимости введите значения по умолчанию для записи команд ключей com.microsoft.SkypeForBusiness с помощью ключей предпочтения, описанных в следующей таблице.
  
**Ключи предпочтения клиента**


| Key | Тип | Значение | Описание |
|:-----|:-----|:-----|:-----|
|autoDetectAutoDicoveryURLs    |Логический    |0 = конфигурация сервера вручную  <br/> 1 = автоматическое обнаружение сервера (по умолчанию)    |Укажите, как Skype для бизнеса определяет транспорт и сервер для использования во время входов. Если этот параметр политики включается, необходимо указать **internalAutoDiscoveryURL** и **externalAutoDiscoveryURL.**   |
|internalAutoDiscoveryURL    |String    |ПОЛНЫЙ URL-адрес автооружия    |ВНУТРЕННИЙ URL-адрес автооружия    |
|externalAutoDiscoveryURL    |String    |ПОЛНЫЙ URL-адрес автооружия    |Внешний URL-адрес автооружия    |
|httpProxyDomain    |String    ||Домен прокси-сервера HTTP    |
|httpProxyUserName    |String    ||HTTP Proxy Username    |
|httpProxyPassword    |String    ||Пароль прокси-сервера HTTP    |
|trustedDomainList    |Массив    ||Список доверенных доменов для перенаправлений HTTP.    |
|autoAcceptTimeout    |Номер    |300 (по умолчанию)    |Auto-Accept timeout for users without Server-side Conversation History.    |
|warnWhenUnknownLocationForE911    |Логический    |0 = отключено  <br/> 1 = включено    |Предупреждает пользователя при наборе номера экстренной службы из неизвестного расположения.    |
|sipAddress    |String    ||SIP-адрес (электронная почта), используемый для входов в Skype для бизнеса.    |
|userName    |String    ||Имя пользователя, используемого для входов в Skype для бизнеса.    |
|userNameInAdvancedOnly    |Логический    |0 = отображать поле "Имя пользователя" на главном экране для входов и в диалоговом окне "Дополнительные свойства"  <br/> 1 = отображать поле "Имя пользователя" только в диалоговом окне "Дополнительные свойства" (по умолчанию)    |Укажите, где будет отображаться поле "Имя пользователя" при входе.    |
   
### <a name="usage-examples"></a>Примеры использования

Чтобы добавить один домен (Contoso.com) в список доверенных доменов, используйте ключ trustedDomainList, как показано ниже:
  
defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "Contoso.com"
  
Чтобы добавить несколько доменов в список доверенных доменов, используйте ключ trustedDomainList, как показано ниже:
  
defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "sfb.com" "abc.com" "test.org"
  
### <a name="sample-unedited-settings"></a>Пример невысвеченных параметров

Для справки вот пример файла параметров с использованием только параметров по умолчанию: 
  
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
