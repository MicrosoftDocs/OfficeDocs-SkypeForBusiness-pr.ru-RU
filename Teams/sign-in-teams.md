---
title: Вход на портал группами Майкрософт
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/23/2018
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Руководство для вход с использованием групп Майкрософт с использованием современных проверки подлинности.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: e7e0f77ee5a98a8c4f28798709dcbc063424ec03
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "25011891"
---
<a name="sign-in-to-microsoft-teams"></a><span data-ttu-id="d4eb7-103">Вход на портал группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d4eb7-103">Sign in to Microsoft Teams</span></span>
==========================

<span data-ttu-id="d4eb7-104">Группами Майкрософт используется современных проверки подлинности для хранения интерфейс входа простой и безопасный.</span><span class="sxs-lookup"><span data-stu-id="d4eb7-104">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="d4eb7-105">Как современные выполняется проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="d4eb7-105">How modern authentication works</span></span>

<span data-ttu-id="d4eb7-106">Современный проверки подлинности — это процесс, который позволяет узнать, что пользователи уже введены в другом месте их учетных данных (например, их работы электронной почты и пароль), и они не нужно вводить их еще раз, чтобы запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="d4eb7-106">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="d4eb7-107">Взаимодействия будет различной в зависимости от нескольких факторов, как при работе в Windows или на Mac.</span><span class="sxs-lookup"><span data-stu-id="d4eb7-107">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="d4eb7-108">Он также может изменяться в зависимости от того, является ли эта возможность разрешена организации проверкой подлинности или многофакторная проверка подлинности (многофакторная проверка подлинности обычно включает в себя проверка учетных данных по телефону, предоставляя уникальный код, ввод ПИН-кода, или представления отпечатком).</span><span class="sxs-lookup"><span data-stu-id="d4eb7-108">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="d4eb7-109">Ниже приводится краткое описание каждого сценария современных проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="d4eb7-109">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="d4eb7-110">Инструкции для пользователей Windows</span><span class="sxs-lookup"><span data-stu-id="d4eb7-110">Windows users</span></span> 

- <span data-ttu-id="d4eb7-111">Если пользователи вошли в других приложений Office через свою учетную запись Office 365 для предприятия, при запуске команды, они будут представлены прямых приложения.</span><span class="sxs-lookup"><span data-stu-id="d4eb7-111">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="d4eb7-112">Нет необходимости их введите свои учетные данные.</span><span class="sxs-lookup"><span data-stu-id="d4eb7-112">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="d4eb7-113">Если пользователи не вошли в учетную запись Office 365 для предприятия в любом другом при запуске команды, они будет предложено ввести проверкой или многофакторной проверки подлинности (SFA или многофакторной проверкой Подлинности), в зависимости от того, что ваша организация решила как процесс включает в себя какую.</span><span class="sxs-lookup"><span data-stu-id="d4eb7-113">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="d4eb7-114">Если пользователи входят в компьютер, присоединенный к домену, начинающим командами, они могут потребовать шла через один шаг проверки подлинности, в зависимости от того, является ли ваша организация подписано для поддержки требования многофакторной проверкой Подлинности или если его компьютер уже требует многофакторной проверкой Подлинности выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="d4eb7-114">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="d4eb7-115">Если компьютер уже требует многофакторной проверкой Подлинности выполнить вход, когда они открываются копирование командами, приложение автоматически запускается.</span><span class="sxs-lookup"><span data-stu-id="d4eb7-115">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

### <a name="mac-users"></a><span data-ttu-id="d4eb7-116">Пользователи Mac</span><span class="sxs-lookup"><span data-stu-id="d4eb7-116">Mac users</span></span> 

<span data-ttu-id="d4eb7-117">При запуске команды, его компьютер не сможет их учетных данных из своей учетной записи Office 365 для предприятия или какие-либо других приложений Office по запросу.</span><span class="sxs-lookup"><span data-stu-id="d4eb7-117">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="d4eb7-118">Вместо этого появится запрос на их SFA или многофакторной проверкой Подлинности (в зависимости от настройки вашей организации).</span><span class="sxs-lookup"><span data-stu-id="d4eb7-118">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="d4eb7-119">После ввода учетных данных, они не требуется предоставить им еще раз.</span><span class="sxs-lookup"><span data-stu-id="d4eb7-119">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="d4eb7-120">С этого момента группы автоматически запускается при каждом при работе на том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="d4eb7-120">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="d4eb7-121">Переключение учетные записи после завершения современных проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="d4eb7-121">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="d4eb7-122">При работе на компьютер, присоединенный к домену, (например, если их клиента включил Kerberos), они не могут переключиться учетные записи пользователей, как только они были завершены современных проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="d4eb7-122">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="d4eb7-123">Если пользователи не работает на компьютер, присоединенный к домену, они переключение учетных записей.</span><span class="sxs-lookup"><span data-stu-id="d4eb7-123">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a><span data-ttu-id="d4eb7-124">Выход из групп Майкрософт после завершения современных проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="d4eb7-124">Signing out of Microsoft Teams after completing modern authentication</span></span>

<span data-ttu-id="d4eb7-125">Чтобы выйти из группы, пользователей можно щелкните изображение их профиля в верхней части приложения и выберите **Выход**. Они также щелкните правой кнопкой мыши значок приложения на панели задач и выберите команду **Выход**. Как только они уже знак вне группы, они должны введите свои учетные данные еще раз, чтобы запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="d4eb7-125">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="d4eb7-126">Устранение неполадок в современном проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="d4eb7-126">Troubleshooting modern authentication</span></span>

<span data-ttu-id="d4eb7-127">Современный проверка подлинности доступна для любой организации, что используется командами, поэтому если пользователям не удается завершить процесс, могут возникнуть ошибки с вашего домена или учетную запись Office 365 корпоративный вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d4eb7-127">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="d4eb7-128">Дополнительные сведения можно [Почему возникают проблемы, вход с использованием групп Майкрософт?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).</span><span class="sxs-lookup"><span data-stu-id="d4eb7-128">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).</span></span>

