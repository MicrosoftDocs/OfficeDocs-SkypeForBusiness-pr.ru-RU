---
title: Настройка клиента на Mac в Skype для бизнеса
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: PhillipGarding
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1d9cfec-e923-4d02-a306-ee40a9114cb8
description: В этой статье описываются параметры клиента Skype для бизнеса на Mac и настройки по умолчанию, а также порядок их изменения вне приложения.
ms.openlocfilehash: 582c9a1b12cf6dd687eff5fe0cb829e1aca98df7
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002659"
---
# <a name="customize-the-mac-client-experience-in-skype-for-business"></a><span data-ttu-id="6c6d2-103">Настройка клиента на Mac в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="6c6d2-103">Customize the Mac client experience in Skype for Business</span></span>
 
<span data-ttu-id="6c6d2-104">В этой статье описываются параметры клиента Skype для бизнеса на Mac и настройки по умолчанию, а также порядок их изменения вне приложения.</span><span class="sxs-lookup"><span data-stu-id="6c6d2-104">This article describes the client preferences and defaults available for the Skype for Business on Mac client, and how to edit them from outside the App.</span></span>
  
## <a name="skype-for-business-on-mac-client-preference-settings"></a><span data-ttu-id="6c6d2-105">Параметры клиента Skype для бизнеса на Mac</span><span class="sxs-lookup"><span data-stu-id="6c6d2-105">Skype for Business on Mac client preference settings</span></span>

<span data-ttu-id="6c6d2-106">Некоторые функции и поведения, доступные для клиентов Skype для бизнеса на компьютерах Mac, определяются параметрами настройки на клиенте.</span><span class="sxs-lookup"><span data-stu-id="6c6d2-106">Certain features and behaviors that are available to Skype for Business on Mac clients are determined by preference settings on the client.</span></span> <span data-ttu-id="6c6d2-107">Параметры Skype для бизнеса для Mac находятся в файле, расположенном на компьютерах Mac, на которых установлен клиент Skype для бизнеса, размещенный по следующему адресу:</span><span class="sxs-lookup"><span data-stu-id="6c6d2-107">The Skype for Business on Mac preferences are found in a file located on Macs that have installed the Skype for Business client located at the following path:</span></span> 
  
 <span data-ttu-id="6c6d2-108">**~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**</span><span class="sxs-lookup"><span data-stu-id="6c6d2-108">**~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**</span></span>
  
<span data-ttu-id="6c6d2-109">Чтобы настроить эти параметры, войдите в запрос терминала на компьютере Mac, а при необходимости введите значения по умолчанию для клавиш com. Microsoft. SkypeForBusiness, используя ключи предпочтений, описанные в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="6c6d2-109">To set these preferences, get to a terminal prompt on the client's Mac and as needed enter defaults write com.microsoft.SkypeForBusiness key commands using the preference keys described in the following table.</span></span>
  
<span data-ttu-id="6c6d2-110">**Ключи параметров клиента**</span><span class="sxs-lookup"><span data-stu-id="6c6d2-110">**Client preference keys**</span></span>


| <span data-ttu-id="6c6d2-111">Ключ</span><span class="sxs-lookup"><span data-stu-id="6c6d2-111">Key</span></span> | <span data-ttu-id="6c6d2-112">Тип</span><span class="sxs-lookup"><span data-stu-id="6c6d2-112">Type</span></span> | <span data-ttu-id="6c6d2-113">Значение</span><span class="sxs-lookup"><span data-stu-id="6c6d2-113">Value</span></span> | <span data-ttu-id="6c6d2-114">Описание</span><span class="sxs-lookup"><span data-stu-id="6c6d2-114">Description</span></span> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6c6d2-115">аутодетектаутодиковерюрлс</span><span class="sxs-lookup"><span data-stu-id="6c6d2-115">autoDetectAutoDicoveryURLs</span></span>    |<span data-ttu-id="6c6d2-116">Bool</span><span class="sxs-lookup"><span data-stu-id="6c6d2-116">Bool</span></span>    |<span data-ttu-id="6c6d2-117">0 = настройка сервера вручную</span><span class="sxs-lookup"><span data-stu-id="6c6d2-117">0 = manual server configuration</span></span>  <br/> <span data-ttu-id="6c6d2-118">1 = автоматическое обнаружение сервера (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="6c6d2-118">1 = automatic server detection (default)</span></span>    |<span data-ttu-id="6c6d2-119">Укажите, как Skype для бизнеса определяет транспорт и сервер для использования при входе.</span><span class="sxs-lookup"><span data-stu-id="6c6d2-119">Specify how Skype for Business identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="6c6d2-120">Включая этот параметр политики, необходимо также указать **internalAutoDiscoveryURL** и **externalAutoDiscoveryURL**.</span><span class="sxs-lookup"><span data-stu-id="6c6d2-120">If you enable this policy setting, you must specify **internalAutoDiscoveryURL** and **externalAutoDiscoveryURL**.</span></span>   |
|<span data-ttu-id="6c6d2-121">internalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="6c6d2-121">internalAutoDiscoveryURL</span></span>    |<span data-ttu-id="6c6d2-122">String</span><span class="sxs-lookup"><span data-stu-id="6c6d2-122">String</span></span>    |<span data-ttu-id="6c6d2-123">URL-адрес службы полного автообнаружения</span><span class="sxs-lookup"><span data-stu-id="6c6d2-123">Full autodiscover URL</span></span>    |<span data-ttu-id="6c6d2-124">URL-адрес службы внутреннего автообнаружения</span><span class="sxs-lookup"><span data-stu-id="6c6d2-124">Internal autodiscover URL</span></span>    |
|<span data-ttu-id="6c6d2-125">externalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="6c6d2-125">externalAutoDiscoveryURL</span></span>    |<span data-ttu-id="6c6d2-126">String</span><span class="sxs-lookup"><span data-stu-id="6c6d2-126">String</span></span>    |<span data-ttu-id="6c6d2-127">URL-адрес службы полного автообнаружения</span><span class="sxs-lookup"><span data-stu-id="6c6d2-127">Full autodiscover URL</span></span>    |<span data-ttu-id="6c6d2-128">URL-адрес службы внешнего автообнаружения</span><span class="sxs-lookup"><span data-stu-id="6c6d2-128">External autodiscover URL</span></span>    |
|<span data-ttu-id="6c6d2-129">httpProxyDomain</span><span class="sxs-lookup"><span data-stu-id="6c6d2-129">httpProxyDomain</span></span>    |<span data-ttu-id="6c6d2-130">String</span><span class="sxs-lookup"><span data-stu-id="6c6d2-130">String</span></span>    ||<span data-ttu-id="6c6d2-131">Домен HTTP-прокси</span><span class="sxs-lookup"><span data-stu-id="6c6d2-131">HTTP Proxy Domain</span></span>    |
|<span data-ttu-id="6c6d2-132">httpProxyUserName</span><span class="sxs-lookup"><span data-stu-id="6c6d2-132">httpProxyUserName</span></span>    |<span data-ttu-id="6c6d2-133">String</span><span class="sxs-lookup"><span data-stu-id="6c6d2-133">String</span></span>    ||<span data-ttu-id="6c6d2-134">Имя пользователя HTTP-прокси</span><span class="sxs-lookup"><span data-stu-id="6c6d2-134">HTTP Proxy Username</span></span>    |
|<span data-ttu-id="6c6d2-135">httpProxyPassword</span><span class="sxs-lookup"><span data-stu-id="6c6d2-135">httpProxyPassword</span></span>    |<span data-ttu-id="6c6d2-136">Строка</span><span class="sxs-lookup"><span data-stu-id="6c6d2-136">String</span></span>    ||<span data-ttu-id="6c6d2-137">Пароль HTTP-прокси</span><span class="sxs-lookup"><span data-stu-id="6c6d2-137">HTTP Proxy Password</span></span>    |
|<span data-ttu-id="6c6d2-138">trustedDomainList</span><span class="sxs-lookup"><span data-stu-id="6c6d2-138">trustedDomainList</span></span>    |<span data-ttu-id="6c6d2-139">Массив</span><span class="sxs-lookup"><span data-stu-id="6c6d2-139">Array</span></span>    ||<span data-ttu-id="6c6d2-140">Список доверенных доменов для перенаправлений HTTP.</span><span class="sxs-lookup"><span data-stu-id="6c6d2-140">List of trusted domains for HTTP redirects.</span></span>    |
|<span data-ttu-id="6c6d2-141">autoAcceptTimeout</span><span class="sxs-lookup"><span data-stu-id="6c6d2-141">autoAcceptTimeout</span></span>    |<span data-ttu-id="6c6d2-142">Число</span><span class="sxs-lookup"><span data-stu-id="6c6d2-142">Number</span></span>    |<span data-ttu-id="6c6d2-143">300 (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="6c6d2-143">300 (default)</span></span>    |<span data-ttu-id="6c6d2-144">Тайм-аут автоматического приема запросов для пользователей, не имеющих журнала бесед на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="6c6d2-144">Auto-Accept timeout for users without Server-side Conversation History.</span></span>    |
|<span data-ttu-id="6c6d2-145">warnWhenUnknownLocationForE911</span><span class="sxs-lookup"><span data-stu-id="6c6d2-145">warnWhenUnknownLocationForE911</span></span>    |<span data-ttu-id="6c6d2-146">Bool</span><span class="sxs-lookup"><span data-stu-id="6c6d2-146">Bool</span></span>    |<span data-ttu-id="6c6d2-147">0 = Отключено</span><span class="sxs-lookup"><span data-stu-id="6c6d2-147">0 = Disabled</span></span>  <br/> <span data-ttu-id="6c6d2-148">1 = Включено</span><span class="sxs-lookup"><span data-stu-id="6c6d2-148">1 = Enabled</span></span>    |<span data-ttu-id="6c6d2-149">Предупреждает пользователя при наборе номера экстренной помощи из неизвестного места.</span><span class="sxs-lookup"><span data-stu-id="6c6d2-149">Warns the user when dialing an emergency number from an unknown location.</span></span>    |
|<span data-ttu-id="6c6d2-150">sipAddress</span><span class="sxs-lookup"><span data-stu-id="6c6d2-150">sipAddress</span></span>    |<span data-ttu-id="6c6d2-151">String</span><span class="sxs-lookup"><span data-stu-id="6c6d2-151">String</span></span>    ||<span data-ttu-id="6c6d2-152">Адрес SIP (электронная почта), используемый для входа в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="6c6d2-152">The SIP address (Email) used to sign-in to Skype for Business.</span></span>    |
|<span data-ttu-id="6c6d2-153">userName</span><span class="sxs-lookup"><span data-stu-id="6c6d2-153">userName</span></span>    |<span data-ttu-id="6c6d2-154">Строка</span><span class="sxs-lookup"><span data-stu-id="6c6d2-154">String</span></span>    ||<span data-ttu-id="6c6d2-155">Имя участника-пользователя (UPN), которое используется для входа в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="6c6d2-155">The UPN (UserName) used to sign-in to Skype for Business.</span></span>    |
|<span data-ttu-id="6c6d2-156">усернамеинадванцедонли</span><span class="sxs-lookup"><span data-stu-id="6c6d2-156">userNameInAdvancedOnly</span></span>    |<span data-ttu-id="6c6d2-157">Bool</span><span class="sxs-lookup"><span data-stu-id="6c6d2-157">Bool</span></span>    |<span data-ttu-id="6c6d2-158">0 = отображать поле "имя пользователя" на главном экране входа и в диалоговом окне "Дополнительные параметры"</span><span class="sxs-lookup"><span data-stu-id="6c6d2-158">0 = display the User Name field on the main sign-in screen and in the Advanced Properties dialog box</span></span>  <br/> <span data-ttu-id="6c6d2-159">1 = отображать поле "имя пользователя" только в диалоговом окне "Дополнительные параметры" (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="6c6d2-159">1 = display the User Name field only in the Advanced Properties dialog box (default)</span></span>    |<span data-ttu-id="6c6d2-160">Укажите, где будет отображаться поле "имя пользователя" во время входа.</span><span class="sxs-lookup"><span data-stu-id="6c6d2-160">Specify where the User Name field is displayed during sign-in.</span></span>    |
   
### <a name="usage-examples"></a><span data-ttu-id="6c6d2-161">Примеры использования</span><span class="sxs-lookup"><span data-stu-id="6c6d2-161">Usage examples</span></span>

<span data-ttu-id="6c6d2-162">Чтобы добавить в список доверенных доменов один домен (Contoso.com), используйте ключ Трустеддомаинлист, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="6c6d2-162">To add a single domain (Contoso.com) to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="6c6d2-163">значения по умолчанию Write com. Microsoft. SkypeForBusiness Трустеддомаинлист-массив-Add "Contoso.com"</span><span class="sxs-lookup"><span data-stu-id="6c6d2-163">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "Contoso.com"</span></span>
  
<span data-ttu-id="6c6d2-164">Чтобы добавить в список доверенных доменов сразу несколько доменов, необходимо воспользоваться ключом trustedDomainList как указано ниже.</span><span class="sxs-lookup"><span data-stu-id="6c6d2-164">To add several domains to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="6c6d2-165">значения по умолчанию Write com. Microsoft. SkypeForBusiness Трустеддомаинлист-массив-Add "sfb.com" "abc.com" "test.org"</span><span class="sxs-lookup"><span data-stu-id="6c6d2-165">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "sfb.com" "abc.com" "test.org"</span></span>
  
### <a name="sample-unedited-settings"></a><span data-ttu-id="6c6d2-166">Пример неизмененных параметров</span><span class="sxs-lookup"><span data-stu-id="6c6d2-166">Sample unedited settings</span></span>

<span data-ttu-id="6c6d2-167">Для справки приведем пример файла параметров, в котором используются только параметры по умолчанию. </span><span class="sxs-lookup"><span data-stu-id="6c6d2-167">For reference, here is a sample settings file using default settings only:</span></span> 
  
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
