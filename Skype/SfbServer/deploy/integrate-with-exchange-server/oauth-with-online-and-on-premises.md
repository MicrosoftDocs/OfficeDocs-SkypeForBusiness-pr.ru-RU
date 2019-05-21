---
title: Интеграция Skype для бизнеса Online и Exchange Server
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Настройка проверки подлинности OAuth между Exchange на локальном и Skype для бизнеса Online включает возможности интеграции Skype для бизнеса и Exchange, описанные в разделе Поддержка функций.
ms.openlocfilehash: be1fd4ae0c1a1046a8da1d9a30550ac238a4034a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278128"
---
# <a name="configure-integration-between-skype-for-business-online-or-microsoft-teams-and-exchange-server"></a><span data-ttu-id="de204-103">Настройка интеграции между Skype для бизнеса Online и Microsoft Teams и Exchange Server</span><span class="sxs-lookup"><span data-stu-id="de204-103">Configure Integration between Skype for Business Online or Microsoft Teams and Exchange Server</span></span> 

<span data-ttu-id="de204-104">Настройка интеграции между Exchange Server и Skype для бизнеса Online включает возможности интеграции Skype для бизнеса и Exchange, описанные в разделе [Поддержка функций](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span><span class="sxs-lookup"><span data-stu-id="de204-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="de204-105">Эта статья относится к интеграции с Exchange Server 2013 – 2019.</span><span class="sxs-lookup"><span data-stu-id="de204-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="de204-106">Что нужно знать перед началом работы?</span><span class="sxs-lookup"><span data-stu-id="de204-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="de204-107">Предполагаемое время выполнения этой задачи: 15 минут</span><span class="sxs-lookup"><span data-stu-id="de204-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="de204-108">Перед выполнением этих процедур вы должны получить разрешения.</span><span class="sxs-lookup"><span data-stu-id="de204-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="de204-109">Чтобы узнать, какие разрешения вам нужны, ознакомьтесь с разделом [разрешения для инфраструктуры Exchange и оболочки](https://go.microsoft.com/fwlink/p/?LinkId=746511) .</span><span class="sxs-lookup"><span data-stu-id="de204-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="de204-110">Сведения о сочетаниях клавиш, которые могут применяться к процедурам, описанным в этой статье, приведены в разделе сочетания [клавиш в центре администрирования Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span><span class="sxs-lookup"><span data-stu-id="de204-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="de204-111">Настройка интеграции между сервером Exchange Server и Office 365</span><span class="sxs-lookup"><span data-stu-id="de204-111">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="de204-112">Действие 1: Настройка проверки подлинности OAuth между Exchange Server и O365</span><span class="sxs-lookup"><span data-stu-id="de204-112">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="de204-113">Выполните действия, описанные в приведенной ниже статье.</span><span class="sxs-lookup"><span data-stu-id="de204-113">Perform the steps in the following article:</span></span>

[<span data-ttu-id="de204-114">Настройка проверки подлинности OAuth между организациями Exchange и Exchange Online</span><span class="sxs-lookup"><span data-stu-id="de204-114">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-or-teams-partner-application"></a><span data-ttu-id="de204-115">Действие 2: создание учетной записи пользователя для партнерской программы Skype для бизнеса Online или Teams</span><span class="sxs-lookup"><span data-stu-id="de204-115">Step 2: Create a new Mail User account for the Skype for Business Online or Teams Partner Application</span></span>

<span data-ttu-id="de204-116">Это действие выполняется на сервере Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="de204-116">This step is done on the Exchange server.</span></span> <span data-ttu-id="de204-117">На этом шаге создается пользователь почты, которому назначаются соответствующие права роли управления.</span><span class="sxs-lookup"><span data-stu-id="de204-117">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="de204-118">Затем эта учетная запись используется на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="de204-118">This account will then be used in the next step.</span></span>

<span data-ttu-id="de204-119">Укажите проверенный домен для организации Exchange.</span><span class="sxs-lookup"><span data-stu-id="de204-119">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="de204-120">Этот домен должен быть тем же доменом, который используется в качестве основного домена SMTP для локальных учетных записей Exchange.</span><span class="sxs-lookup"><span data-stu-id="de204-120">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="de204-121">Этот домен называется \<проверяемым доменом\> в описанной ниже процедуре.</span><span class="sxs-lookup"><span data-stu-id="de204-121">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="de204-122">Кроме того, \<домаинконтроллерфкдн\> должно быть полным доменным именем контроллера домена.</span><span class="sxs-lookup"><span data-stu-id="de204-122">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

``` Powershell
$user = New-MailUser -Name O365-ApplicationAccount -ExternalEmailAddress O365-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="de204-123">Эта команда скрывает нового пользователя почты из списка адресов.</span><span class="sxs-lookup"><span data-stu-id="de204-123">This command will hide the new mail user from address lists.</span></span>

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="de204-124">Следующие две команды назначают новой учетной записи роль управления UserApplication и ArchiveApplication.</span><span class="sxs-lookup"><span data-stu-id="de204-124">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online-or-teams"></a><span data-ttu-id="de204-125">Шаг 3: создание и включение приложения-партнера для Skype для бизнеса Online или Teams</span><span class="sxs-lookup"><span data-stu-id="de204-125">Step 3: Create and enable a Partner Application for Skype for Business Online or Teams</span></span>

<span data-ttu-id="de204-126">Создайте новое партнерское приложение и начните использовать созданную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="de204-126">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="de204-127">Выполните следующую команду в PowerShell Exchange в локальной организации Exchange.</span><span class="sxs-lookup"><span data-stu-id="de204-127">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="verify-your-success"></a><span data-ttu-id="de204-128">Проверка успешности выполнения</span><span class="sxs-lookup"><span data-stu-id="de204-128">Verify your success</span></span>

<span data-ttu-id="de204-129">Убедитесь в том, что конфигурация верна, проверьте, успешно ли работают некоторые функции.</span><span class="sxs-lookup"><span data-stu-id="de204-129">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="de204-130">Убедитесь в том, что делегирование календаря Outlook работает в бетвиен двух пользователей Teams с Exchange Server 2016 или 2019.</span><span class="sxs-lookup"><span data-stu-id="de204-130">Confirm Outlook Calendar delegation works betweeen two Teams users with Exchange Server 2016 or 2019 mailboxes.</span></span>

2. <span data-ttu-id="de204-131">Убедитесь в том, что в папке "Журнал бесед" Outlook отображается журнал бесед для мобильных клиентов.</span><span class="sxs-lookup"><span data-stu-id="de204-131">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

<span data-ttu-id="de204-132">Кроме того, Взгляните на трафик.</span><span class="sxs-lookup"><span data-stu-id="de204-132">Alternately, look at your traffic.</span></span> <span data-ttu-id="de204-133">Трафик в подтверждении OAuth является весьма отличительным (и не рассматривается как обычная проверка подлинности), особенно вокруг сфер, где вы начнете просматривать трафик поставщика, выглядящий следующим образом: 00000004-0000-0ff1-ce00-000000000000 @ (иногда с a/Before знак "@") в токенах, которые передаются.</span><span class="sxs-lookup"><span data-stu-id="de204-133">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="de204-134">Вы не увидите имя пользователя или пароль, который является точкой OAuth.</span><span class="sxs-lookup"><span data-stu-id="de204-134">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="de204-135">Но вы увидите, что в этом случае это "4" — Skype для бизнеса — и сфера подписки.</span><span class="sxs-lookup"><span data-stu-id="de204-135">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="de204-136">Если вы хотите, чтобы вы успешно использовали OAuth, убедитесь, что вы знаете, что нужно ожидать и что нужно знать, как выглядит трафик.</span><span class="sxs-lookup"><span data-stu-id="de204-136">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="de204-137">Итак, вот [что нужно ожидать](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34): Вот стандартный [пример трафика OAuth в приложении Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (это может оказаться полезным для чтения, но не использует маркеры обновления), и есть расширения Fiddler, позволяющие найти OAuth JWT (JSON). Веб-токен).</span><span class="sxs-lookup"><span data-stu-id="de204-137">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="de204-138">Ниже приведен [Пример настройки одного из них](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), но вы можете использовать любой сетевой инструмент трассировки, который вы хотите предпринять.</span><span class="sxs-lookup"><span data-stu-id="de204-138">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="de204-139">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="de204-139">Related topics</span></span>

[<span data-ttu-id="de204-140">Настройка проверки подлинности OAuth между организациями Exchange и Exchange Online</span><span class="sxs-lookup"><span data-stu-id="de204-140">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
