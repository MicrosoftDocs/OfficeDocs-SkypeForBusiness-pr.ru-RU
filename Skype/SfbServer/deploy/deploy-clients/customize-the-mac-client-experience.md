---
title: Настройка клиента на Mac в Skype для бизнеса
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1d9cfec-e923-4d02-a306-ee40a9114cb8
description: В этой статье описываются параметры клиента Skype для бизнеса на Mac и настройки по умолчанию, а также порядок их изменения вне приложения.
ms.openlocfilehash: 37ea82cc87e58303ab412c7adbd427dd11c74f89
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21014642"
---
# <a name="customize-the-mac-client-experience-in-skype-for-business"></a><span data-ttu-id="a2440-103">Настройка клиента на Mac в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a2440-103">Customize the Mac client experience in Skype for Business</span></span>
 
<span data-ttu-id="a2440-104">В этой статье описываются параметры клиента Skype для бизнеса на Mac и настройки по умолчанию, а также порядок их изменения вне приложения.</span><span class="sxs-lookup"><span data-stu-id="a2440-104">This article describes the client preferences and defaults available for the Skype for Business on Mac client, and how to edit them from outside the App.</span></span>
  
## <a name="skype-for-business-on-mac-client-preference-settings"></a><span data-ttu-id="a2440-105">Параметры клиента Skype для бизнеса на Mac</span><span class="sxs-lookup"><span data-stu-id="a2440-105">Skype for Business on Mac client preference settings</span></span>

<span data-ttu-id="a2440-106">Некоторые функции и поведения, доступных для Скайп для бизнеса на клиентов, определяются настройки на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="a2440-106">Certain features and behaviors that are available to Skype for Business on Mac clients are determined by preference settings on the client.</span></span> <span data-ttu-id="a2440-107">Скайп для бизнеса на Mac предпочтения находятся в файл, расположенный на компьютерах Mac. установленных Скайп для клиента Business, расположенном по следующему пути:</span><span class="sxs-lookup"><span data-stu-id="a2440-107">The Skype for Business on Mac preferences are found in a file located on Macs that have installed the Skype for Business client located at the following path:</span></span> 
  
 <span data-ttu-id="a2440-108">**~/Library/Containers/COM.Microsoft.SkypeForBusiness/Data/Library/Preferences/COM.Microsoft.SkypeForBusiness.plist**</span><span class="sxs-lookup"><span data-stu-id="a2440-108">**~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**</span></span>
  
<span data-ttu-id="a2440-109">Чтобы задать эти параметры, получения командной строки в Mac клиента и в качестве необходимо ввести значения по умолчанию и записи com.microsoft.SkypeForBusiness клавиш с помощью клавиш предпочтений, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="a2440-109">To set these preferences, get to a terminal prompt on the client's Mac and as needed enter defaults write com.microsoft.SkypeForBusiness key commands using the preference keys described in the following table.</span></span>
  
<span data-ttu-id="a2440-110">**Ключи параметров клиента**</span><span class="sxs-lookup"><span data-stu-id="a2440-110">**Client preference keys**</span></span>


|<span data-ttu-id="a2440-111">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="a2440-111">**Key**</span></span>|<span data-ttu-id="a2440-112">**Тип**</span><span class="sxs-lookup"><span data-stu-id="a2440-112">**Type**</span></span>|<span data-ttu-id="a2440-113">**Значение**</span><span class="sxs-lookup"><span data-stu-id="a2440-113">**Value**</span></span>|<span data-ttu-id="a2440-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a2440-114">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a2440-115">AutoDetectAutoDicoveryURLs</span><span class="sxs-lookup"><span data-stu-id="a2440-115">AutoDetectAutoDicoveryURLs</span></span>  <br/> |<span data-ttu-id="a2440-116">Bool</span><span class="sxs-lookup"><span data-stu-id="a2440-116">Bool</span></span>  <br/> |<span data-ttu-id="a2440-117">0 = настройка сервера вручную</span><span class="sxs-lookup"><span data-stu-id="a2440-117">0 = manual server configuration</span></span>  <br/> <span data-ttu-id="a2440-118">1 = автоматическое обнаружение сервера (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="a2440-118">1 = automatic server detection (default)</span></span>  <br/> |<span data-ttu-id="a2440-119">Укажите, как идентифицирует Скайп для бизнеса, транспортный сервер и сервер, используемый при входе в систему.</span><span class="sxs-lookup"><span data-stu-id="a2440-119">Specify how Skype for Business identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="a2440-120">Включая этот параметр политики, необходимо также указать **internalAutoDiscoveryURL** и **externalAutoDiscoveryURL**.</span><span class="sxs-lookup"><span data-stu-id="a2440-120">If you enable this policy setting, you must specify **internalAutoDiscoveryURL** and **externalAutoDiscoveryURL**.</span></span> <br/> |
|<span data-ttu-id="a2440-121">internalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="a2440-121">internalAutoDiscoveryURL</span></span>  <br/> |<span data-ttu-id="a2440-122">Строка</span><span class="sxs-lookup"><span data-stu-id="a2440-122">String</span></span>  <br/> |<span data-ttu-id="a2440-123">URL-адрес службы полного автообнаружения</span><span class="sxs-lookup"><span data-stu-id="a2440-123">Full autodiscover URL</span></span>  <br/> |<span data-ttu-id="a2440-124">URL-адрес службы внутреннего автообнаружения</span><span class="sxs-lookup"><span data-stu-id="a2440-124">Internal autodiscover URL</span></span>  <br/> |
|<span data-ttu-id="a2440-125">externalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="a2440-125">externalAutoDiscoveryURL</span></span>  <br/> |<span data-ttu-id="a2440-126">Строка</span><span class="sxs-lookup"><span data-stu-id="a2440-126">String</span></span>  <br/> |<span data-ttu-id="a2440-127">URL-адрес службы полного автообнаружения</span><span class="sxs-lookup"><span data-stu-id="a2440-127">Full autodiscover URL</span></span>  <br/> |<span data-ttu-id="a2440-128">URL-адрес службы внешнего автообнаружения</span><span class="sxs-lookup"><span data-stu-id="a2440-128">External autodiscover URL</span></span>  <br/> |
|<span data-ttu-id="a2440-129">httpProxyDomain</span><span class="sxs-lookup"><span data-stu-id="a2440-129">httpProxyDomain</span></span>  <br/> |<span data-ttu-id="a2440-130">Строка</span><span class="sxs-lookup"><span data-stu-id="a2440-130">String</span></span>  <br/> ||<span data-ttu-id="a2440-131">Домен HTTP-прокси</span><span class="sxs-lookup"><span data-stu-id="a2440-131">HTTP Proxy Domain</span></span>  <br/> |
|<span data-ttu-id="a2440-132">httpProxyUserName</span><span class="sxs-lookup"><span data-stu-id="a2440-132">httpProxyUserName</span></span>  <br/> |<span data-ttu-id="a2440-133">Строка</span><span class="sxs-lookup"><span data-stu-id="a2440-133">String</span></span>  <br/> ||<span data-ttu-id="a2440-134">Имя пользователя HTTP-прокси</span><span class="sxs-lookup"><span data-stu-id="a2440-134">HTTP Proxy Username</span></span>  <br/> |
|<span data-ttu-id="a2440-135">httpProxyPassword</span><span class="sxs-lookup"><span data-stu-id="a2440-135">httpProxyPassword</span></span>  <br/> |<span data-ttu-id="a2440-136">Строка</span><span class="sxs-lookup"><span data-stu-id="a2440-136">String</span></span>  <br/> ||<span data-ttu-id="a2440-137">Пароль HTTP-прокси</span><span class="sxs-lookup"><span data-stu-id="a2440-137">HTTP Proxy Password</span></span>  <br/> |
|<span data-ttu-id="a2440-138">trustedDomainList</span><span class="sxs-lookup"><span data-stu-id="a2440-138">trustedDomainList</span></span>  <br/> |<span data-ttu-id="a2440-139">Массив</span><span class="sxs-lookup"><span data-stu-id="a2440-139">Array</span></span>  <br/> ||<span data-ttu-id="a2440-140">Список доверенных доменов для перенаправлений HTTP.</span><span class="sxs-lookup"><span data-stu-id="a2440-140">List of trusted domains for HTTP redirects.</span></span>  <br/> |
|<span data-ttu-id="a2440-141">autoAcceptTimeout</span><span class="sxs-lookup"><span data-stu-id="a2440-141">autoAcceptTimeout</span></span>  <br/> |<span data-ttu-id="a2440-142">Число</span><span class="sxs-lookup"><span data-stu-id="a2440-142">Number</span></span>  <br/> |<span data-ttu-id="a2440-143">300 (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="a2440-143">300 (default)</span></span>  <br/> |<span data-ttu-id="a2440-144">Тайм-аут автоматического приема запросов для пользователей, не имеющих журнала бесед на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="a2440-144">Auto-Accept timeout for users without Server-side Conversation History.</span></span>  <br/> |
|<span data-ttu-id="a2440-145">warnWhenUnknownLocationForE911</span><span class="sxs-lookup"><span data-stu-id="a2440-145">warnWhenUnknownLocationForE911</span></span>  <br/> |<span data-ttu-id="a2440-146">Bool</span><span class="sxs-lookup"><span data-stu-id="a2440-146">Bool</span></span>  <br/> |<span data-ttu-id="a2440-147">0 = Отключено</span><span class="sxs-lookup"><span data-stu-id="a2440-147">0 = Disabled</span></span>  <br/> <span data-ttu-id="a2440-148">1 = Включено</span><span class="sxs-lookup"><span data-stu-id="a2440-148">1 = Enabled</span></span>  <br/> |<span data-ttu-id="a2440-149">Предупреждает пользователя при наборе номера экстренной помощи из неизвестного места.</span><span class="sxs-lookup"><span data-stu-id="a2440-149">Warns the user when dialing an emergency number from an unknown location.</span></span>  <br/> |
|<span data-ttu-id="a2440-150">sipAddress</span><span class="sxs-lookup"><span data-stu-id="a2440-150">sipAddress</span></span>  <br/> |<span data-ttu-id="a2440-151">Строка</span><span class="sxs-lookup"><span data-stu-id="a2440-151">String</span></span>  <br/> ||<span data-ttu-id="a2440-152">Адрес SIP (электронной почты), используемый для входа в систему для Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a2440-152">The SIP address (Email) used to sign-in to Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="a2440-153">имя пользователя</span><span class="sxs-lookup"><span data-stu-id="a2440-153">userName</span></span>  <br/> |<span data-ttu-id="a2440-154">Строка</span><span class="sxs-lookup"><span data-stu-id="a2440-154">String</span></span>  <br/> ||<span data-ttu-id="a2440-155">Имя участника-пользователя (имя пользователя) используется для входа в систему для Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a2440-155">The UPN (UserName) used to sign-in to Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="a2440-156">userNameInAdvancedOnly</span><span class="sxs-lookup"><span data-stu-id="a2440-156">userNameInAdvancedOnly</span></span>  <br/> |<span data-ttu-id="a2440-157">Bool</span><span class="sxs-lookup"><span data-stu-id="a2440-157">Bool</span></span>  <br/> |<span data-ttu-id="a2440-158">0 = отображения в поле имя пользователя на главном экране входа и в диалоговом окне Дополнительные свойства</span><span class="sxs-lookup"><span data-stu-id="a2440-158">0 = display the User Name field on the main sign-in screen and in the Advanced Properties dialog box</span></span>  <br/> <span data-ttu-id="a2440-159">1 = отображения поля имя пользователя только в диалоговое окно "Дополнительные свойства" (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="a2440-159">1 = display the User Name field only in the Advanced Properties dialog box (default)</span></span>  <br/> |<span data-ttu-id="a2440-160">Укажите, где отображается в поле имя пользователя при входе в систему.</span><span class="sxs-lookup"><span data-stu-id="a2440-160">Specify where the User Name field is displayed during sign-in.</span></span>  <br/> |
   
### <a name="usage-examples"></a><span data-ttu-id="a2440-161">Примеры использования</span><span class="sxs-lookup"><span data-stu-id="a2440-161">Usage examples</span></span>

<span data-ttu-id="a2440-162">Добавление в список доверенных доменов одного домена (Contoso.com) будет использовать ключ trustedDomainList, как показано:</span><span class="sxs-lookup"><span data-stu-id="a2440-162">To add a single domain (Contoso.com) to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="a2440-163">значения по умолчанию запись com.microsoft.SkypeForBusiness trustedDomainList-массива — Добавление «Contoso.com»</span><span class="sxs-lookup"><span data-stu-id="a2440-163">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "Contoso.com"</span></span>
  
<span data-ttu-id="a2440-164">Чтобы добавить в список доверенных доменов сразу несколько доменов, необходимо воспользоваться ключом trustedDomainList как указано ниже.</span><span class="sxs-lookup"><span data-stu-id="a2440-164">To add several domains to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="a2440-165">значения по умолчанию запись com.microsoft.SkypeForBusiness trustedDomainList-массива — Добавление «sfb.com» «abc.com» «test.org»</span><span class="sxs-lookup"><span data-stu-id="a2440-165">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "sfb.com" "abc.com" "test.org"</span></span>
  
  
### <a name="sample-unedited-settings"></a><span data-ttu-id="a2440-166">Пример неизмененных параметров</span><span class="sxs-lookup"><span data-stu-id="a2440-166">Sample unedited settings</span></span>

<span data-ttu-id="a2440-167">Для справки приведем пример файла параметров, в котором используются только параметры по умолчанию. </span><span class="sxs-lookup"><span data-stu-id="a2440-167">For reference, here is a sample settings file using default settings only:</span></span> 
  
```
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


