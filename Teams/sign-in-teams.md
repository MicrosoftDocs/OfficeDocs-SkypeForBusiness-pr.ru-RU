---
title: Вход в Microsoft Teams с современной проверкой подлинности
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/15/2018
audience: Admin
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Вход в Microsoft Teams с использованием современной проверки подлинности.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5698058cbfecd62f92cfe9f198657f7c280deff
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "37563124"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="5dc49-103">Вход в Microsoft Teams с современной проверкой подлинности</span><span class="sxs-lookup"><span data-stu-id="5dc49-103">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="5dc49-104">В Microsoft Teams используется современная проверка подлинности для обеспечения простой и безопасной работы входа.</span><span class="sxs-lookup"><span data-stu-id="5dc49-104">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="5dc49-105">Чтобы узнать, как пользователи входят в Teams, прочтите раздел [Вход в Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span><span class="sxs-lookup"><span data-stu-id="5dc49-105">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="5dc49-106">Принцип работы современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="5dc49-106">How modern authentication works</span></span>

<span data-ttu-id="5dc49-107">Современная проверка подлинности — это процесс, в соответствии с которым пользователи уже ввели свои учетные данные (например, рабочие адреса электронной почты и пароли) в другом месте и не должны вводить их повторно, чтобы запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="5dc49-107">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="5dc49-108">Этот интерфейс будет зависеть от нескольких факторов, например, если пользователи работают в Windows или на компьютере Mac.</span><span class="sxs-lookup"><span data-stu-id="5dc49-108">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="5dc49-109">Оно также варьируется в зависимости от того, включена ли в вашей организации Однофакторная проверка подлинности или многофакторная проверка подлинности (обычно используется для проверки учетных данных с помощью телефона, предоставления уникального кода, ввода ПИН-кода или представление отпечатка.</span><span class="sxs-lookup"><span data-stu-id="5dc49-109">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="5dc49-110">Ниже приведено краткое описание каждого сценария современной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="5dc49-110">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="5dc49-111">Инструкции для пользователей Windows</span><span class="sxs-lookup"><span data-stu-id="5dc49-111">Windows users</span></span> 

- <span data-ttu-id="5dc49-112">Если пользователи уже вошли в другие приложения Office через свою учетную запись Office 365, то при запуске команд, которые они переводят прямо в приложение.</span><span class="sxs-lookup"><span data-stu-id="5dc49-112">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="5dc49-113">Вводить учетные данные не нужно.</span><span class="sxs-lookup"><span data-stu-id="5dc49-113">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="5dc49-114">Если пользователи не вошли в свою учетную запись Office 365, где бы вы ни находились, то при запуске Teams вам будет предложено использовать однофакторную или многофакторную проверку подлинности (СФА или MFA) в зависимости от того, что ваша организация решила вам. процесс.</span><span class="sxs-lookup"><span data-stu-id="5dc49-114">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="5dc49-115">Если пользователи вошли в систему на компьютере, подключенном к домену, при запуске Teams может потребоваться пройти еще один шаг проверки подлинности в зависимости от того, требуется ли в вашей организации необходимость в MFA, либо на том случае, если для входа в систему уже требуется MFA.</span><span class="sxs-lookup"><span data-stu-id="5dc49-115">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="5dc49-116">Если на вашем компьютере уже требуется MFA для входа, то при открытии Teams приложение автоматически запускается.</span><span class="sxs-lookup"><span data-stu-id="5dc49-116">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

### <a name="mac-users"></a><span data-ttu-id="5dc49-117">Пользователи Mac</span><span class="sxs-lookup"><span data-stu-id="5dc49-117">Mac users</span></span> 

<span data-ttu-id="5dc49-118">Когда пользователи запускают Teams, они не смогут получать свои учетные данные из своей учетной записи Office 365 и других приложений Office.</span><span class="sxs-lookup"><span data-stu-id="5dc49-118">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="5dc49-119">Вместо этого они будут видеть запрос на СФА или MFA (в зависимости от настроек вашей организации).</span><span class="sxs-lookup"><span data-stu-id="5dc49-119">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="5dc49-120">После того как пользователи вводят свои учетные данные, они не будут требовать их повторного предоставления.</span><span class="sxs-lookup"><span data-stu-id="5dc49-120">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="5dc49-121">С этого момента Teams автоматически запускается каждый раз, когда они работают на одном и том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="5dc49-121">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="5dc49-122">Переключение учетных записей после завершения современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="5dc49-122">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="5dc49-123">Если пользователи работают на компьютере, подключенном к домену (например, если его клиент включил протокол Kerberos), они не смогут переключать учетные записи после выполнения современной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="5dc49-123">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="5dc49-124">Если пользователи не работают на компьютере, подключенном к домену, они могут переключать учетные записи.</span><span class="sxs-lookup"><span data-stu-id="5dc49-124">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a><span data-ttu-id="5dc49-125">Выход из Microsoft Teams после выполнения современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="5dc49-125">Signing out of Microsoft Teams after completing modern authentication</span></span>
<span data-ttu-id="5dc49-126">Чтобы выйти из Teams, пользователи могут щелкнуть аватар в верхней части приложения, а затем выбрать команду **выход**. Кроме того, они могут щелкнуть правой кнопкой мыши значок приложения на панели задач, а затем выбрать команду **выход**. После того как вы выйдете из Teams, ему нужно будет повторно ввести свои учетные данные, чтобы запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="5dc49-126">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="5dc49-127">Устранение неполадок современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="5dc49-127">Troubleshooting modern authentication</span></span>

<span data-ttu-id="5dc49-128">Современная проверка подлинности доступна для каждой организации, использующей Teams, поэтому если пользователи не могут завершить процесс, возможно, у вас возникли проблемы с вашим доменом или учетной записью Office 365 вашей компании.</span><span class="sxs-lookup"><span data-stu-id="5dc49-128">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="5dc49-129">Дополнительные сведения можно найти в статье Почему не удается [войти в Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span><span class="sxs-lookup"><span data-stu-id="5dc49-129">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).</span></span>

