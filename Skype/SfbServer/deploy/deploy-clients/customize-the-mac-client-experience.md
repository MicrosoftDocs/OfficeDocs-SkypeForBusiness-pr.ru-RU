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
# <a name="customize-the-mac-client-experience-in-skype-for-business"></a><span data-ttu-id="2714e-103">Настройка клиентского опыта Mac в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2714e-103">Customize the Mac client experience in Skype for Business</span></span>
 
<span data-ttu-id="2714e-104">В этой статье описаны параметры клиента и параметры по умолчанию, доступные для клиента Skype для бизнеса на Mac, а также их редактирование из-за пределов приложения.</span><span class="sxs-lookup"><span data-stu-id="2714e-104">This article describes the client preferences and defaults available for the Skype for Business on Mac client, and how to edit them from outside the App.</span></span>
  
## <a name="skype-for-business-on-mac-client-preference-settings"></a><span data-ttu-id="2714e-105">Параметры параметров клиента Skype для бизнеса на Mac</span><span class="sxs-lookup"><span data-stu-id="2714e-105">Skype for Business on Mac client preference settings</span></span>

<span data-ttu-id="2714e-106">Некоторые функции и поведение, доступные клиентам Skype для бизнеса на Mac, определяются настройками параметров клиента.</span><span class="sxs-lookup"><span data-stu-id="2714e-106">Certain features and behaviors that are available to Skype for Business on Mac clients are determined by preference settings on the client.</span></span> <span data-ttu-id="2714e-107">Параметры Skype для бизнеса на Mac находятся в файле, расположенном на компьютере Mac с установленным клиентом Skype для бизнеса, расположенным по следующему пути:</span><span class="sxs-lookup"><span data-stu-id="2714e-107">The Skype for Business on Mac preferences are found in a file located on Macs that have installed the Skype for Business client located at the following path:</span></span> 
  
 <span data-ttu-id="2714e-108">**~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**</span><span class="sxs-lookup"><span data-stu-id="2714e-108">**~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**</span></span>
  
<span data-ttu-id="2714e-109">Чтобы настроить эти параметры, перейдите к запросу терминала на компьютере Mac клиента и при необходимости введите значения по умолчанию для записи команд ключей com.microsoft.SkypeForBusiness с помощью ключей предпочтения, описанных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="2714e-109">To set these preferences, get to a terminal prompt on the client's Mac and as needed enter defaults write com.microsoft.SkypeForBusiness key commands using the preference keys described in the following table.</span></span>
  
<span data-ttu-id="2714e-110">**Ключи предпочтения клиента**</span><span class="sxs-lookup"><span data-stu-id="2714e-110">**Client preference keys**</span></span>


| <span data-ttu-id="2714e-111">Key</span><span class="sxs-lookup"><span data-stu-id="2714e-111">Key</span></span> | <span data-ttu-id="2714e-112">Тип</span><span class="sxs-lookup"><span data-stu-id="2714e-112">Type</span></span> | <span data-ttu-id="2714e-113">Значение</span><span class="sxs-lookup"><span data-stu-id="2714e-113">Value</span></span> | <span data-ttu-id="2714e-114">Описание</span><span class="sxs-lookup"><span data-stu-id="2714e-114">Description</span></span> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2714e-115">autoDetectAutoDicoveryURLs</span><span class="sxs-lookup"><span data-stu-id="2714e-115">autoDetectAutoDicoveryURLs</span></span>    |<span data-ttu-id="2714e-116">Логический</span><span class="sxs-lookup"><span data-stu-id="2714e-116">Bool</span></span>    |<span data-ttu-id="2714e-117">0 = конфигурация сервера вручную</span><span class="sxs-lookup"><span data-stu-id="2714e-117">0 = manual server configuration</span></span>  <br/> <span data-ttu-id="2714e-118">1 = автоматическое обнаружение сервера (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="2714e-118">1 = automatic server detection (default)</span></span>    |<span data-ttu-id="2714e-119">Укажите, как Skype для бизнеса определяет транспорт и сервер для использования во время входов.</span><span class="sxs-lookup"><span data-stu-id="2714e-119">Specify how Skype for Business identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="2714e-120">Если этот параметр политики включается, необходимо указать **internalAutoDiscoveryURL** и **externalAutoDiscoveryURL.**</span><span class="sxs-lookup"><span data-stu-id="2714e-120">If you enable this policy setting, you must specify **internalAutoDiscoveryURL** and **externalAutoDiscoveryURL**.</span></span>   |
|<span data-ttu-id="2714e-121">internalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="2714e-121">internalAutoDiscoveryURL</span></span>    |<span data-ttu-id="2714e-122">String</span><span class="sxs-lookup"><span data-stu-id="2714e-122">String</span></span>    |<span data-ttu-id="2714e-123">ПОЛНЫЙ URL-адрес автооружия</span><span class="sxs-lookup"><span data-stu-id="2714e-123">Full autodiscover URL</span></span>    |<span data-ttu-id="2714e-124">ВНУТРЕННИЙ URL-адрес автооружия</span><span class="sxs-lookup"><span data-stu-id="2714e-124">Internal autodiscover URL</span></span>    |
|<span data-ttu-id="2714e-125">externalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="2714e-125">externalAutoDiscoveryURL</span></span>    |<span data-ttu-id="2714e-126">String</span><span class="sxs-lookup"><span data-stu-id="2714e-126">String</span></span>    |<span data-ttu-id="2714e-127">ПОЛНЫЙ URL-адрес автооружия</span><span class="sxs-lookup"><span data-stu-id="2714e-127">Full autodiscover URL</span></span>    |<span data-ttu-id="2714e-128">Внешний URL-адрес автооружия</span><span class="sxs-lookup"><span data-stu-id="2714e-128">External autodiscover URL</span></span>    |
|<span data-ttu-id="2714e-129">httpProxyDomain</span><span class="sxs-lookup"><span data-stu-id="2714e-129">httpProxyDomain</span></span>    |<span data-ttu-id="2714e-130">String</span><span class="sxs-lookup"><span data-stu-id="2714e-130">String</span></span>    ||<span data-ttu-id="2714e-131">Домен прокси-сервера HTTP</span><span class="sxs-lookup"><span data-stu-id="2714e-131">HTTP Proxy Domain</span></span>    |
|<span data-ttu-id="2714e-132">httpProxyUserName</span><span class="sxs-lookup"><span data-stu-id="2714e-132">httpProxyUserName</span></span>    |<span data-ttu-id="2714e-133">String</span><span class="sxs-lookup"><span data-stu-id="2714e-133">String</span></span>    ||<span data-ttu-id="2714e-134">HTTP Proxy Username</span><span class="sxs-lookup"><span data-stu-id="2714e-134">HTTP Proxy Username</span></span>    |
|<span data-ttu-id="2714e-135">httpProxyPassword</span><span class="sxs-lookup"><span data-stu-id="2714e-135">httpProxyPassword</span></span>    |<span data-ttu-id="2714e-136">String</span><span class="sxs-lookup"><span data-stu-id="2714e-136">String</span></span>    ||<span data-ttu-id="2714e-137">Пароль прокси-сервера HTTP</span><span class="sxs-lookup"><span data-stu-id="2714e-137">HTTP Proxy Password</span></span>    |
|<span data-ttu-id="2714e-138">trustedDomainList</span><span class="sxs-lookup"><span data-stu-id="2714e-138">trustedDomainList</span></span>    |<span data-ttu-id="2714e-139">Массив</span><span class="sxs-lookup"><span data-stu-id="2714e-139">Array</span></span>    ||<span data-ttu-id="2714e-140">Список доверенных доменов для перенаправлений HTTP.</span><span class="sxs-lookup"><span data-stu-id="2714e-140">List of trusted domains for HTTP redirects.</span></span>    |
|<span data-ttu-id="2714e-141">autoAcceptTimeout</span><span class="sxs-lookup"><span data-stu-id="2714e-141">autoAcceptTimeout</span></span>    |<span data-ttu-id="2714e-142">Номер</span><span class="sxs-lookup"><span data-stu-id="2714e-142">Number</span></span>    |<span data-ttu-id="2714e-143">300 (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="2714e-143">300 (default)</span></span>    |<span data-ttu-id="2714e-144">Auto-Accept timeout for users without Server-side Conversation History.</span><span class="sxs-lookup"><span data-stu-id="2714e-144">Auto-Accept timeout for users without Server-side Conversation History.</span></span>    |
|<span data-ttu-id="2714e-145">warnWhenUnknownLocationForE911</span><span class="sxs-lookup"><span data-stu-id="2714e-145">warnWhenUnknownLocationForE911</span></span>    |<span data-ttu-id="2714e-146">Логический</span><span class="sxs-lookup"><span data-stu-id="2714e-146">Bool</span></span>    |<span data-ttu-id="2714e-147">0 = отключено</span><span class="sxs-lookup"><span data-stu-id="2714e-147">0 = Disabled</span></span>  <br/> <span data-ttu-id="2714e-148">1 = включено</span><span class="sxs-lookup"><span data-stu-id="2714e-148">1 = Enabled</span></span>    |<span data-ttu-id="2714e-149">Предупреждает пользователя при наборе номера экстренной службы из неизвестного расположения.</span><span class="sxs-lookup"><span data-stu-id="2714e-149">Warns the user when dialing an emergency number from an unknown location.</span></span>    |
|<span data-ttu-id="2714e-150">sipAddress</span><span class="sxs-lookup"><span data-stu-id="2714e-150">sipAddress</span></span>    |<span data-ttu-id="2714e-151">String</span><span class="sxs-lookup"><span data-stu-id="2714e-151">String</span></span>    ||<span data-ttu-id="2714e-152">SIP-адрес (электронная почта), используемый для входов в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="2714e-152">The SIP address (Email) used to sign-in to Skype for Business.</span></span>    |
|<span data-ttu-id="2714e-153">userName</span><span class="sxs-lookup"><span data-stu-id="2714e-153">userName</span></span>    |<span data-ttu-id="2714e-154">String</span><span class="sxs-lookup"><span data-stu-id="2714e-154">String</span></span>    ||<span data-ttu-id="2714e-155">Имя пользователя, используемого для входов в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="2714e-155">The UPN (UserName) used to sign-in to Skype for Business.</span></span>    |
|<span data-ttu-id="2714e-156">userNameInAdvancedOnly</span><span class="sxs-lookup"><span data-stu-id="2714e-156">userNameInAdvancedOnly</span></span>    |<span data-ttu-id="2714e-157">Логический</span><span class="sxs-lookup"><span data-stu-id="2714e-157">Bool</span></span>    |<span data-ttu-id="2714e-158">0 = отображать поле "Имя пользователя" на главном экране для входов и в диалоговом окне "Дополнительные свойства"</span><span class="sxs-lookup"><span data-stu-id="2714e-158">0 = display the User Name field on the main sign-in screen and in the Advanced Properties dialog box</span></span>  <br/> <span data-ttu-id="2714e-159">1 = отображать поле "Имя пользователя" только в диалоговом окне "Дополнительные свойства" (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="2714e-159">1 = display the User Name field only in the Advanced Properties dialog box (default)</span></span>    |<span data-ttu-id="2714e-160">Укажите, где будет отображаться поле "Имя пользователя" при входе.</span><span class="sxs-lookup"><span data-stu-id="2714e-160">Specify where the User Name field is displayed during sign-in.</span></span>    |
   
### <a name="usage-examples"></a><span data-ttu-id="2714e-161">Примеры использования</span><span class="sxs-lookup"><span data-stu-id="2714e-161">Usage examples</span></span>

<span data-ttu-id="2714e-162">Чтобы добавить один домен (Contoso.com) в список доверенных доменов, используйте ключ trustedDomainList, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="2714e-162">To add a single domain (Contoso.com) to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="2714e-163">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "Contoso.com"</span><span class="sxs-lookup"><span data-stu-id="2714e-163">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "Contoso.com"</span></span>
  
<span data-ttu-id="2714e-164">Чтобы добавить несколько доменов в список доверенных доменов, используйте ключ trustedDomainList, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="2714e-164">To add several domains to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="2714e-165">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "sfb.com" "abc.com" "test.org"</span><span class="sxs-lookup"><span data-stu-id="2714e-165">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "sfb.com" "abc.com" "test.org"</span></span>
  
### <a name="sample-unedited-settings"></a><span data-ttu-id="2714e-166">Пример невысвеченных параметров</span><span class="sxs-lookup"><span data-stu-id="2714e-166">Sample unedited settings</span></span>

<span data-ttu-id="2714e-167">Для справки вот пример файла параметров с использованием только параметров по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="2714e-167">For reference, here is a sample settings file using default settings only:</span></span> 
  
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
