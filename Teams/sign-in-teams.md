---
title: Вход в Teams с современной проверкой подлинности
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Узнайте, как работает современная проверка подлинности, как переключаться между учетными записями и как устранять неполадки с современной проверкой подлинности.
ms.custom: seo-marvel-apr2020
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 344cf0d38926af200f4d92b664761d2c8868df57
ms.sourcegitcommit: c3f44fccdbd9178d30b52bb0db6f6d31a6dd174b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "44139142"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="8f6ae-103">Вход в Microsoft Teams с современной проверкой подлинности</span><span class="sxs-lookup"><span data-stu-id="8f6ae-103">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="8f6ae-104">В Microsoft Teams используется современная проверка подлинности, чтобы обеспечить простой и безопасный вход в систему.</span><span class="sxs-lookup"><span data-stu-id="8f6ae-104">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="8f6ae-105">Чтобы узнать, как пользователи входят в Teams, см. статью [Вход в Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span><span class="sxs-lookup"><span data-stu-id="8f6ae-105">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="8f6ae-106">Принцип работы современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="8f6ae-106">How modern authentication works</span></span>

<span data-ttu-id="8f6ae-107">Современная проверка подлинности — это процесс, с помощью которого приложение Teams узнает, что пользователи уже ввели свои учетные данные (например, рабочий адрес электронной почты и пароль) в другом месте и им не требуется вводить их повторно, чтобы запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="8f6ae-107">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="8f6ae-108">Интерфейс зависит от нескольких факторов, например от использования Windows или компьютера Mac.</span><span class="sxs-lookup"><span data-stu-id="8f6ae-108">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="8f6ae-109">Он также изменяется в зависимости от того, включена ли в вашей организации однофакторная или многофакторная проверка подлинности (при многофакторной проверке подлинности обычно используется проверка учетных данных с помощью телефона, предоставления уникального кода, ввода ПИН-кода или представления отпечатка пальца).</span><span class="sxs-lookup"><span data-stu-id="8f6ae-109">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="8f6ae-110">Ниже приведено краткое описание каждого сценария современной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="8f6ae-110">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="8f6ae-111">Пользователи Windows</span><span class="sxs-lookup"><span data-stu-id="8f6ae-111">Windows users</span></span> 

- <span data-ttu-id="8f6ae-112">Если пользователи уже вошли в другие приложения Office с помощью своей учетной записи Office 365 корпоративный, при запуске Teams они будут направлены сразу в приложение.</span><span class="sxs-lookup"><span data-stu-id="8f6ae-112">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="8f6ae-113">Им не потребуется вводить свои учетные данные.</span><span class="sxs-lookup"><span data-stu-id="8f6ae-113">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="8f6ae-114">Если пользователи не выполняли вход в свою учетную запись Office 365 корпоративный в другом месте, при запуске Teams им будет предложено пройти однофакторную или многофакторную проверку подлинности (SFA или MFA) в зависимости от выбранного процесса в организации.</span><span class="sxs-lookup"><span data-stu-id="8f6ae-114">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="8f6ae-115">Если пользователи выполнили вход на компьютере, подключенном к домену, при запуске Teams может потребоваться пройти еще один шаг проверки подлинности. Это зависит от того, выбрана ли в организации обязательная MFA или компьютер сразу требует MFA для входа.</span><span class="sxs-lookup"><span data-stu-id="8f6ae-115">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="8f6ae-116">Если компьютер сразу требует MFA для входа, при открытии Teams приложение запускается автоматически.</span><span class="sxs-lookup"><span data-stu-id="8f6ae-116">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

- <span data-ttu-id="8f6ae-117">Если пользователи выполнили вход на компьютере, подключенном к домену, и вы **не хотите, чтобы их имена предварительно добавлялись на экран входа в Teams**, администраторы могут настроить следующий раздел реестра Windows для отключения предварительного заполнения имени пользователя (UPN):</span><span class="sxs-lookup"><span data-stu-id="8f6ae-117">If users are signed in to a domain-joined computer and you **don't want their user name pre-populated on the Teams sign-in screen**, admins can set the following Windows registry to turn off pre-population of the user name (UPN):</span></span>

  <span data-ttu-id="8f6ae-118">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="8f6ae-118">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="8f6ae-119">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="8f6ae-119">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="8f6ae-120">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="8f6ae-120">0x00000001 (1)</span></span>

  <span data-ttu-id="8f6ae-121">Если вы используете Outlook 2013 или 2016, ознакомьтесь со статьей [Обновление для пропуска поиска имени участника-пользователя (UPN) в Outlook 2016 и 2013](https://support.microsoft.com/help/4022165/update-to-skip-user-principal-name-upn-lookup-in-outlook-2016-and-2013)</span><span class="sxs-lookup"><span data-stu-id="8f6ae-121">If you're running Outlook 2013 or 2016, read [Update to skip the user principal name (UPN) lookup in Outlook 2016 and 2013](https://support.microsoft.com/help/4022165/update-to-skip-user-principal-name-upn-lookup-in-outlook-2016-and-2013)</span></span>

    > [!NOTE]
    > <span data-ttu-id="8f6ae-122">Пропуск или игнорирование предварительного добавления имен пользователей, оканчивающихся на ".local" или ".corp", включено по умолчанию, поэтому вам не нужно настраивать раздел реестра для их отключения.</span><span class="sxs-lookup"><span data-stu-id="8f6ae-122">Skipping or ignoring user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span> 


### <a name="mac-users"></a><span data-ttu-id="8f6ae-123">Пользователи компьютеров Mac</span><span class="sxs-lookup"><span data-stu-id="8f6ae-123">Mac users</span></span> 

<span data-ttu-id="8f6ae-124">При запуске пользователем приложения Teams его компьютер на сможет извлечь учетные данные из учетной записи Office 365 корпоративный или других приложений Office.</span><span class="sxs-lookup"><span data-stu-id="8f6ae-124">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="8f6ae-125">Вместо этого отобразится запрос на SFA или MFA (зависит от параметров организации).</span><span class="sxs-lookup"><span data-stu-id="8f6ae-125">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="8f6ae-126">После ввода пользователем учетных данных ему не потребуется указывать их снова.</span><span class="sxs-lookup"><span data-stu-id="8f6ae-126">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="8f6ae-127">С этого момента Teams будет запускаться автоматически при работе пользователя на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="8f6ae-127">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="8f6ae-128">Переключение учетных записей после выполнения современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="8f6ae-128">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="8f6ae-129">Если пользователь работает на компьютере, подключенном к домену (например, если в клиенте включен протокол Kerberos), ему не удастся переключить учетные записи после выполнения современной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="8f6ae-129">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="8f6ae-130">Если рабочий компьютер пользователя не подключен к домену, он сможет переключить учетную запись.</span><span class="sxs-lookup"><span data-stu-id="8f6ae-130">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a><span data-ttu-id="8f6ae-131">Выход из Teams после выполнения современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="8f6ae-131">Signing out of Teams after completing modern authentication</span></span>
<span data-ttu-id="8f6ae-132">Для выхода из Teams пользователи могут щелкнуть свой аватар в верхней части окна приложения и выбрать команду **Выйти**. Кроме того, они могут щелкнуть правой кнопкой мыши значок приложения на панели задач и выбрать команду **Выйти**. После выхода из Teams пользователю потребуется повторно ввести свои учетные данные, чтобы запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="8f6ae-132">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="urls-and-ip-address-ranges"></a><span data-ttu-id="8f6ae-133">URL-адреса и диапазоны IP-адресов</span><span class="sxs-lookup"><span data-stu-id="8f6ae-133">URLs and IP address ranges</span></span>
<span data-ttu-id="8f6ae-134">Для Teams требуется подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="8f6ae-134">Teams requires connectivity to the Internet.</span></span> <span data-ttu-id="8f6ae-135">Для ознакомления с конечными точками, которые должны быть доступны для клиентов, использующих Teams в планах Office 365, государственных и других облаках, см. статью [URL-адреса и диапазоны IP-адресов Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="8f6ae-135">To understand endpoints that should be reachable for customers using Teams in Office 365 plans, Government and other clouds, read [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="8f6ae-136">В настоящее время Teams требует доступ (порт TCP 443) к службе Google ssl.gstatic.com (https://ssl.gstatic.com) для всех пользователей, даже если вы не используете Gstatic.</span><span class="sxs-lookup"><span data-stu-id="8f6ae-136">Teams presently requires access (TCP port 443) to the Google ssl.gstatic.com service (https://ssl.gstatic.com) for all users; this is true even if you're not using Gstatic.</span></span> <span data-ttu-id="8f6ae-137">Скоро (в начале 2020 г.) это требование будет удалено из Teams, и мы обновим эту статью соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="8f6ae-137">Teams will remove this requirement soon (early 2020), and we'll update this article accordingly at that time.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="8f6ae-138">Устранение неполадок с современной проверкой подлинности</span><span class="sxs-lookup"><span data-stu-id="8f6ae-138">Troubleshooting modern authentication</span></span>

<span data-ttu-id="8f6ae-139">Современная проверка подлинности доступна для каждой организации, использующей Teams, поэтому если пользователи не могут завершить процесс, возможно, у вас возникли проблемы с вашим доменом или учетной записью Office 365 корпоративный вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8f6ae-139">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="8f6ae-140">Дополнительные сведения см. в статье [Почему у меня возникают проблемы со входом в Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span><span class="sxs-lookup"><span data-stu-id="8f6ae-140">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span></span>

