---
title: Виртуальные посещения с помощью Microsoft Teams и приложения Bookings
author: msdmaguire
ms.author: dmaguire
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Microsoft Teams и виртуальные посещения с помощью приложения Bookings
ms.openlocfilehash: 582c59b4c389d687c529a7db9d9f1825d488f9f3
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125752"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a><span data-ttu-id="d1060-103">Виртуальные посещения с помощью Microsoft Teams и приложения Bookings</span><span class="sxs-lookup"><span data-stu-id="d1060-103">Virtual visits with Microsoft Teams and the Bookings app</span></span>

<span data-ttu-id="d1060-104">Приложение Bookings в Microsoft Teams предлагает простой способ запланировать линую и виртуальную встречу, например посещение здравоохранения, консультации по финансам, собеседования, поддержку клиентов, учебные часы и многое другое.</span><span class="sxs-lookup"><span data-stu-id="d1060-104">The Bookings app in Microsoft Teams offers a simple way to schedule in-person and virtual appointments, such as healthcare visits, financial consultations, interviews, customer support, education office hours, and much more.</span></span>

<span data-ttu-id="d1060-105">Планиры могут управлять несколькими календарями отделов и сотрудников, а также общением с внутренними и внешними участниками из единого взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="d1060-105">Schedulers can manage multiple department and staff calendars, as well as communications with internal and external attendees, from a single experience.</span></span> <span data-ttu-id="d1060-106">Виртуальные встречи проводятся с помощью собраний Microsoft Teams, что обеспечивает надежные возможности видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="d1060-106">The virtual appointments themselves are held via Microsoft Teams Meetings, which offers robust videoconferencing capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="d1060-107">Только планиры должны иметь приложение Bookings, установленное в Teams.</span><span class="sxs-lookup"><span data-stu-id="d1060-107">Only schedulers need to have the Bookings app installed in Teams.</span></span> <span data-ttu-id="d1060-108">Приложение не требуется для проведения виртуальных встреч или участия в них сотрудников.</span><span class="sxs-lookup"><span data-stu-id="d1060-108">Staff conducting or participating in virtual appointments do not need the app.</span></span> <span data-ttu-id="d1060-109">Они могут просто присоединиться к встречам из календаря Outlook или Teams или по ссылке в сообщении с подтверждением резервирования.</span><span class="sxs-lookup"><span data-stu-id="d1060-109">They can simply join appointments from their Outlook or Teams calendar or from a link in their booking confirmation email.</span></span>

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a><span data-ttu-id="d1060-110">Предварительные условия для использования приложения Bookings в Teams</span><span class="sxs-lookup"><span data-stu-id="d1060-110">Prerequisites for using the Bookings app in Teams</span></span>

- <span data-ttu-id="d1060-111">Почтовый ящик Exchange должен быть в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d1060-111">The Exchange mailbox must be in Exchange Online.</span></span> <span data-ttu-id="d1060-112">Локальное Exchange Server не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="d1060-112">On-premises Exchange Server mailboxes are not supported.</span></span>

- <span data-ttu-id="d1060-113">Для организации должна быть включена служба Microsoft Bookings.</span><span class="sxs-lookup"><span data-stu-id="d1060-113">Microsoft Bookings must be turned on for the organization.</span></span>

- <span data-ttu-id="d1060-114">У пользователей должна быть соответствующая лицензия.</span><span class="sxs-lookup"><span data-stu-id="d1060-114">Users must have an appropriate license.</span></span> <span data-ttu-id="d1060-115">Поддерживаются Office 365 A3, A5, E3 и E5, а также Microsoft 365 бизнес стандартный, A3, A5, E3 и E5.</span><span class="sxs-lookup"><span data-stu-id="d1060-115">Office 365 A3, A5, E3, and E5, as well as Microsoft 365 Business Standard, A3, A5, E3, and E5 are supported.</span></span>

- <span data-ttu-id="d1060-116">У всех пользователей приложения Bookings и всех сотрудников, участвующих в собраниях, должна быть лицензия, которая поддерживает планирование собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="d1060-116">All users of the Bookings app and all staff participating in meetings must have a license that supports Teams Meeting scheduling.</span></span>

- <span data-ttu-id="d1060-117">Ваши системы должны соответствовать всем требованиям [к Программному обеспечению и браузеру.](hardware-requirements-for-the-teams-app.md)</span><span class="sxs-lookup"><span data-stu-id="d1060-117">Your systems must meet all [Software and browser prerequisites](hardware-requirements-for-the-teams-app.md).</span></span>

## <a name="availability-of-bookings-in-teams"></a><span data-ttu-id="d1060-118">Доступность Bookings в Teams</span><span class="sxs-lookup"><span data-stu-id="d1060-118">Availability of Bookings in Teams</span></span>

<span data-ttu-id="d1060-119">Приложение Microsoft Bookings для Teams доступно в классических и веб-приложениях.</span><span class="sxs-lookup"><span data-stu-id="d1060-119">Microsoft Bookings App for Teams is available on the desktop and web.</span></span> <span data-ttu-id="d1060-120">Его можно найти в приложениях  [в Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) и в центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="d1060-120">It can be found under [Apps within Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) and under **Manage Apps** within Teams Admin Center.</span></span>

### <a name="control-access-to-bookings-within-your-organization"></a><span data-ttu-id="d1060-121">Управление доступом к Bookings в организации</span><span class="sxs-lookup"><span data-stu-id="d1060-121">Control access to Bookings within your organization</span></span>

<span data-ttu-id="d1060-122">Существует несколько способов контроля доступа к приложению Bookings и его функциям.</span><span class="sxs-lookup"><span data-stu-id="d1060-122">There are several ways to control who has access to the Bookings app and to specific features of the app.</span></span> <span data-ttu-id="d1060-123">Чтобы узнать, как включить или отключить Microsoft Bookings в Центре администрирования Microsoft 365, а также как создать политику приложения Bookings, разрешаемую выбранным пользователям создавать календари [Bookings,](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)см. в этом случае.</span><span class="sxs-lookup"><span data-stu-id="d1060-123">To learn how to turn Microsoft Bookings on or off in the Microsoft 365 admin center, as well as how to create a Bookings app policy to allow selected users to create Bookings calendars, see [Get access to Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span></span> <span data-ttu-id="d1060-124">Вы также можете узнать, как создать политику приложения Teams, чтобы закрепить [приложение Bookings для отдельных пользователей.](teams-app-setup-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d1060-124">You can also learn how to [Create a Teams app policy to pin the Bookings app for select users](teams-app-setup-policies.md).</span></span>

## <a name="recommended-meeting-policy-settings"></a><span data-ttu-id="d1060-125">Рекомендуемые параметры политики собраний</span><span class="sxs-lookup"><span data-stu-id="d1060-125">Recommended Meeting Policy Settings</span></span>

<span data-ttu-id="d1060-126">Чтобы обеспечить наилучшее впечатление от работы с Bookings, создайте политику собраний для сотрудников, чтобы автоматически допустить **всех сотрудников в организации.**</span><span class="sxs-lookup"><span data-stu-id="d1060-126">To enable the best experience for Bookings, create a staff meeting policy to automatically admit **Everyone in your organization**.</span></span> <span data-ttu-id="d1060-127">Это позволит сотрудникам автоматически присоединяться к встрече и включить возможности "вести", когда внешние участники будут присутствовать на собраниях.</span><span class="sxs-lookup"><span data-stu-id="d1060-127">This will allow staff to join the appointment automatically and enable lobby experience for external attendees.</span></span> <span data-ttu-id="d1060-128">Дополнительные данные об автоматическом [допуске людей на собрания.](meeting-policies-in-teams.md#automatically-admit-people)</span><span class="sxs-lookup"><span data-stu-id="d1060-128">You can learn more about [automatically admitting people to meetings](meeting-policies-in-teams.md#automatically-admit-people).</span></span>

### <a name="optional-staff-approvals-setting"></a><span data-ttu-id="d1060-129">Необязательный параметр утверждения сотрудников</span><span class="sxs-lookup"><span data-stu-id="d1060-129">Optional staff approvals setting</span></span>

<span data-ttu-id="d1060-130">В качестве дополнительного параметра конфиденциальности вы можете потребовать от сотрудников делиться сведениями о доступности по расписанию через Bookings и резервировать их для встречи.</span><span class="sxs-lookup"><span data-stu-id="d1060-130">As an extra privacy setting, you can choose to require staff to opt in before their schedule availability information is shared through Bookings and before they can be booked for an appointment.</span></span>  

<span data-ttu-id="d1060-131">Чтобы включить этот параметр, перейдите в параметры Центра администрирования **Microsoft 365** и выберите \>  \>  **"Bookings".**</span><span class="sxs-lookup"><span data-stu-id="d1060-131">To enable this setting, go to **Microsoft 365 admin center** \> **Settings** \> **Settings**, then select **Bookings**.</span></span>

<span data-ttu-id="d1060-132">Если этот параметр включен, сотрудники получают сообщение электронной почты с запросом на утверждение членства в календаре резервирования.</span><span class="sxs-lookup"><span data-stu-id="d1060-132">With this setting turned on, staff will receive an email in which they are asked to approve membership to a booking calendar.</span></span>  

<span data-ttu-id="d1060-133">Эта функция постепенно становится общенародной для клиентов Microsoft 365 и Office 365.</span><span class="sxs-lookup"><span data-stu-id="d1060-133">This feature is gradually being rolled out worldwide to Microsoft 365 and Office 365 customers.</span></span> <span data-ttu-id="d1060-134">Если в вашей среде пока нет всех параметров, проверьте их в ближайшее время.</span><span class="sxs-lookup"><span data-stu-id="d1060-134">If all options are not yet available in your environment, check back soon.</span></span>

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a><span data-ttu-id="d1060-135">Изменение домена по умолчанию при настройке почтовых ящиков Bookings</span><span class="sxs-lookup"><span data-stu-id="d1060-135">Changing your default domain when setting up Bookings mailboxes</span></span>

<span data-ttu-id="d1060-136">При настройке почтового ящика Bookings используется стандартный домен электронной почты вашей организации Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="d1060-136">When setting up a Bookings mailbox, the default email domain of your Microsoft 365 or Office 365 organization is used.</span></span> <span data-ttu-id="d1060-137">Однако это может привести к проблемам при отправке приглашений на собрания внешним получателям. Ваше приглашение может быть помечено как нежелательное и перемещено в папку нежелательной почты получателя, чтобы получатель не видел ваше приглашение.</span><span class="sxs-lookup"><span data-stu-id="d1060-137">However, this can cause problems when sending meeting invites to external recipients; your invite might be flagged as spam and moved to the recipient’s junk folder, so the recipient might never see your invite.</span></span>

<span data-ttu-id="d1060-138">Рекомендуем изменить домен по умолчанию перед созданием почтового ящика Bookings.</span><span class="sxs-lookup"><span data-stu-id="d1060-138">We recommend that you change the default domain prior to creating your Bookings mailbox.</span></span> <span data-ttu-id="d1060-139">Сведения о том, как это сделать, см. в вопросе и вопросе о [доменах.](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="d1060-139">For information on how to do this, see the [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span></span>

<span data-ttu-id="d1060-140">Если вам нужно изменить домен по умолчанию после создания почтового ящика Bookings, вы можете сделать это с помощью PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d1060-140">If you need to change the default domain after your Bookings mailbox has already been created, you can do so with PowerShell:</span></span>

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

<span data-ttu-id="d1060-141">Дополнительные сведения см. в документации PowerShell для [cmdlet Set-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)</span><span class="sxs-lookup"><span data-stu-id="d1060-141">For more information, see the PowerShell documentation for the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="d1060-142">Если используется гибридная конфигурация Exchange, мы рекомендуем тщательно проверить потоки почты между локальной сетью Exchange и Exchange Online при изменении домена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d1060-142">If you are using an Exchange hybrid configuration, we recommend that you thoroughly test mail flow between on-premises Exchange and Exchange Online when changing the default domain.</span></span>

## <a name="sending-feedback"></a><span data-ttu-id="d1060-143">Отправка отзыва</span><span class="sxs-lookup"><span data-stu-id="d1060-143">Sending feedback</span></span>

<span data-ttu-id="d1060-144">Мы будем рады вашим отзывам о:</span><span class="sxs-lookup"><span data-stu-id="d1060-144">We welcome your feedback on:</span></span>

  - <span data-ttu-id="d1060-145">Пользовательский интерфейс и простота использования</span><span class="sxs-lookup"><span data-stu-id="d1060-145">User experience or ease of use</span></span>
  - <span data-ttu-id="d1060-146">Недочеты функций или отсутствие функций</span><span class="sxs-lookup"><span data-stu-id="d1060-146">Feature gaps or missing functionality</span></span>
  - <span data-ttu-id="d1060-147">Ошибки и проблемы</span><span class="sxs-lookup"><span data-stu-id="d1060-147">Bugs or issues</span></span>
  
<span data-ttu-id="d1060-148">Чтобы отправить отзыв, нажмите кнопку **"Справка"** в нижней части левой панели навигации Teams, а затем выберите "Сообщить о проблеме **для ВСЕХ** проблем". </span><span class="sxs-lookup"><span data-stu-id="d1060-148">To send feedback, click the **Help** button near the bottom of the Teams left navigation bar, then click **Report a Problem** for **ALL** issues.</span></span> <span data-ttu-id="d1060-149">Обратите внимание в начале отчета о том, что вы отправляете отзыв о bookings, чтобы мы могли легко определить проблемы с Bookings.</span><span class="sxs-lookup"><span data-stu-id="d1060-149">Please note at the beginning of your feedback report that you are sending feedback about "Bookings" so we can easily identify Bookings issues.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d1060-150">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d1060-150">Related topics</span></span>

[<span data-ttu-id="d1060-151">Документация по Bookings для конечных пользователей</span><span class="sxs-lookup"><span data-stu-id="d1060-151">Bookings documentation for end users</span></span>](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
