---
title: Виртуальные визиты с помощью Microsoft Teams и приложения Bookings
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
description: Приложение Bookings и виртуальные визиты в Microsoft Teams
ms.openlocfilehash: 582c59b4c389d687c529a7db9d9f1825d488f9f3
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125752"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a><span data-ttu-id="1aa14-103">Виртуальные визиты с помощью Microsoft Teams и приложения Bookings</span><span class="sxs-lookup"><span data-stu-id="1aa14-103">Virtual visits with Microsoft Teams and the Bookings app</span></span>

<span data-ttu-id="1aa14-104">Приложение Bookings в Microsoft Teams предлагает простой способ запланировать личные и виртуальные встречи, например посещение врача, финансовые консультации, собеседования, поддержку клиентов, учебные часы и многое другое.</span><span class="sxs-lookup"><span data-stu-id="1aa14-104">The Bookings app in Microsoft Teams offers a simple way to schedule in-person and virtual appointments, such as healthcare visits, financial consultations, interviews, customer support, education office hours, and much more.</span></span>

<span data-ttu-id="1aa14-105">Планировщики могут управлять несколькими календарями отделов и сотрудников, а также взаимодействием с внутренними и внешними участниками одной встречи.</span><span class="sxs-lookup"><span data-stu-id="1aa14-105">Schedulers can manage multiple department and staff calendars, as well as communications with internal and external attendees, from a single experience.</span></span> <span data-ttu-id="1aa14-106">Сами виртуальные встречи проводятся с помощью собраний Microsoft Teams, что обеспечивает надежные возможности видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="1aa14-106">The virtual appointments themselves are held via Microsoft Teams Meetings, which offers robust videoconferencing capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="1aa14-107">Приложение Bookings необходимо устанавливать только для планировщиков в Teams.</span><span class="sxs-lookup"><span data-stu-id="1aa14-107">Only schedulers need to have the Bookings app installed in Teams.</span></span> <span data-ttu-id="1aa14-108">Сотрудники, участвующие в виртуальных встречах или проводящие их, не нуждаются в этом приложении.</span><span class="sxs-lookup"><span data-stu-id="1aa14-108">Staff conducting or participating in virtual appointments do not need the app.</span></span> <span data-ttu-id="1aa14-109">Они могут просто присоединяться к встречам из календаря Outlook или Teams или по ссылке в электронном письме с подтверждением резервирования.</span><span class="sxs-lookup"><span data-stu-id="1aa14-109">They can simply join appointments from their Outlook or Teams calendar or from a link in their booking confirmation email.</span></span>

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a><span data-ttu-id="1aa14-110">Необходимые условия для использования приложения Bookings в Teams</span><span class="sxs-lookup"><span data-stu-id="1aa14-110">Prerequisites for using the Bookings app in Teams</span></span>

- <span data-ttu-id="1aa14-111">Почтовый ящик Exchange должен быть в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1aa14-111">The Exchange mailbox must be in Exchange Online.</span></span> <span data-ttu-id="1aa14-112">Почтовые ящики, размещенные на локальном сервере Exchange Server, не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="1aa14-112">On-premises Exchange Server mailboxes are not supported.</span></span>

- <span data-ttu-id="1aa14-113">Для организации должна быть включена служба Microsoft Bookings.</span><span class="sxs-lookup"><span data-stu-id="1aa14-113">Microsoft Bookings must be turned on for the organization.</span></span>

- <span data-ttu-id="1aa14-114">У пользователей должна быть соответствующая лицензия.</span><span class="sxs-lookup"><span data-stu-id="1aa14-114">Users must have an appropriate license.</span></span> <span data-ttu-id="1aa14-115">Поддерживаются Office 365 A3, A5, E3 и E5, а также Microsoft 365 бизнес стандарт, A3, A5, E3 и E5.</span><span class="sxs-lookup"><span data-stu-id="1aa14-115">Office 365 A3, A5, E3, and E5, as well as Microsoft 365 Business Standard, A3, A5, E3, and E5 are supported.</span></span>

- <span data-ttu-id="1aa14-116">У всех пользователей приложения Bookings и всех сотрудников, участвующих в собраниях, должна быть лицензия, которая поддерживает планирование собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="1aa14-116">All users of the Bookings app and all staff participating in meetings must have a license that supports Teams Meeting scheduling.</span></span>

- <span data-ttu-id="1aa14-117">Ваши системы должны соответствовать всем [требованиям к программному обеспечению и браузеру](hardware-requirements-for-the-teams-app.md).</span><span class="sxs-lookup"><span data-stu-id="1aa14-117">Your systems must meet all [Software and browser prerequisites](hardware-requirements-for-the-teams-app.md).</span></span>

## <a name="availability-of-bookings-in-teams"></a><span data-ttu-id="1aa14-118">Доступность Bookings в Teams</span><span class="sxs-lookup"><span data-stu-id="1aa14-118">Availability of Bookings in Teams</span></span>

<span data-ttu-id="1aa14-119">Приложение Microsoft Bookings для Teams доступно в классической и Интернет-версии.</span><span class="sxs-lookup"><span data-stu-id="1aa14-119">Microsoft Bookings App for Teams is available on the desktop and web.</span></span> <span data-ttu-id="1aa14-120">Его можно найти в [приложениях в Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) и в разделе **Управление приложениями** в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="1aa14-120">It can be found under [Apps within Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) and under **Manage Apps** within Teams Admin Center.</span></span>

### <a name="control-access-to-bookings-within-your-organization"></a><span data-ttu-id="1aa14-121">Управление доступом к Bookings в организации</span><span class="sxs-lookup"><span data-stu-id="1aa14-121">Control access to Bookings within your organization</span></span>

<span data-ttu-id="1aa14-122">Существует несколько способов управления доступом к приложению Bookings и определенным функциям приложения.</span><span class="sxs-lookup"><span data-stu-id="1aa14-122">There are several ways to control who has access to the Bookings app and to specific features of the app.</span></span> <span data-ttu-id="1aa14-123">Чтобы узнать, как включить или отключить Microsoft Bookings в Центре администрирования Microsoft 365, а также как создать политику приложения Bookings, чтобы разрешить выбранным пользователям создавать календари Bookings, см. [Получить доступ к Microsoft Bookings](https://support.microsoft.com/ru-RU/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span><span class="sxs-lookup"><span data-stu-id="1aa14-123">To learn how to turn Microsoft Bookings on or off in the Microsoft 365 admin center, as well as how to create a Bookings app policy to allow selected users to create Bookings calendars, see [Get access to Microsoft Bookings](https://support.microsoft.com/ru-RU/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span></span> <span data-ttu-id="1aa14-124">Вы также можете узнать, как [создать политику приложений Teams, чтобы закрепить приложение Bookings для выбранных пользователей](teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1aa14-124">You can also learn how to [Create a Teams app policy to pin the Bookings app for select users](teams-app-setup-policies.md).</span></span>

## <a name="recommended-meeting-policy-settings"></a><span data-ttu-id="1aa14-125">Рекомендуемые параметры политики собраний</span><span class="sxs-lookup"><span data-stu-id="1aa14-125">Recommended Meeting Policy Settings</span></span>

<span data-ttu-id="1aa14-126">Чтобы было удобнее всего работать с Bookings, создайте политику собраний персонала, которая автоматически допустит **Всех сотрудников организации**.</span><span class="sxs-lookup"><span data-stu-id="1aa14-126">To enable the best experience for Bookings, create a staff meeting policy to automatically admit **Everyone in your organization**.</span></span> <span data-ttu-id="1aa14-127">Это позволит сотрудникам автоматически присоединяться к встрече и обеспечит возможность присоединения для внешних участников.</span><span class="sxs-lookup"><span data-stu-id="1aa14-127">This will allow staff to join the appointment automatically and enable lobby experience for external attendees.</span></span> <span data-ttu-id="1aa14-128">Узнайте больше об [автоматическом допуске на собрания](meeting-policies-in-teams.md#automatically-admit-people).</span><span class="sxs-lookup"><span data-stu-id="1aa14-128">You can learn more about [automatically admitting people to meetings](meeting-policies-in-teams.md#automatically-admit-people).</span></span>

### <a name="optional-staff-approvals-setting"></a><span data-ttu-id="1aa14-129">Дополнительная настройка согласования с сотрудниками</span><span class="sxs-lookup"><span data-stu-id="1aa14-129">Optional staff approvals setting</span></span>

<span data-ttu-id="1aa14-130">В качестве дополнительного параметра конфиденциальности вы можете указать, что сотрудники должны выразить свое согласие на участие прежде, чем сведения о доступности расписания будут опубликованы через Bookings и для этих сотрудников может быть запланировано собрание.</span><span class="sxs-lookup"><span data-stu-id="1aa14-130">As an extra privacy setting, you can choose to require staff to opt in before their schedule availability information is shared through Bookings and before they can be booked for an appointment.</span></span>  

<span data-ttu-id="1aa14-131">Чтобы включить эту настройку, перейдите в **Центр администрирования Microsoft 365** \> **Параметры** \> **Параметры**, а затем выберите **Bookings**.</span><span class="sxs-lookup"><span data-stu-id="1aa14-131">To enable this setting, go to **Microsoft 365 admin center** \> **Settings** \> **Settings**, then select **Bookings**.</span></span>

<span data-ttu-id="1aa14-132">Если этот параметр включен, сотрудники получат сообщение электронной почты, в котором им предложат согласиться на участие в календаре резервирования.</span><span class="sxs-lookup"><span data-stu-id="1aa14-132">With this setting turned on, staff will receive an email in which they are asked to approve membership to a booking calendar.</span></span>  

<span data-ttu-id="1aa14-133">Эта функция будет постепенно развертываться по всему миру для пользователей Microsoft 365 и Office 365.</span><span class="sxs-lookup"><span data-stu-id="1aa14-133">This feature is gradually being rolled out worldwide to Microsoft 365 and Office 365 customers.</span></span> <span data-ttu-id="1aa14-134">Если в вашей среде пока доступны не все возможности, проверяйте время от времени, не изменилась ли ситуация.</span><span class="sxs-lookup"><span data-stu-id="1aa14-134">If all options are not yet available in your environment, check back soon.</span></span>

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a><span data-ttu-id="1aa14-135">Изменение домена по умолчанию при настройке почтовых ящиков Bookings</span><span class="sxs-lookup"><span data-stu-id="1aa14-135">Changing your default domain when setting up Bookings mailboxes</span></span>

<span data-ttu-id="1aa14-136">При настройке почтового ящика Bookings используется домен электронной почты по умолчанию вашей организации Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="1aa14-136">When setting up a Bookings mailbox, the default email domain of your Microsoft 365 or Office 365 organization is used.</span></span> <span data-ttu-id="1aa14-137">Однако это может привести к проблемам при отправке приглашений на собрание внешним получателям; ваше приглашение может быть помечено как спам и перемещено в папку нежелательной почты, и получатель может никогда не увидеть ваше приглашение.</span><span class="sxs-lookup"><span data-stu-id="1aa14-137">However, this can cause problems when sending meeting invites to external recipients; your invite might be flagged as spam and moved to the recipient’s junk folder, so the recipient might never see your invite.</span></span>

<span data-ttu-id="1aa14-138">Перед созданием почтового ящика Bookings рекомендуется изменить домен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1aa14-138">We recommend that you change the default domain prior to creating your Bookings mailbox.</span></span> <span data-ttu-id="1aa14-139">Сведения о том, как это сделать, см. в разделе [Вопросы и ответы по доменам](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="1aa14-139">For information on how to do this, see the [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span></span>

<span data-ttu-id="1aa14-140">Если после создания почтового ящика Bookings нужно изменить домен по умолчанию, это можно сделать с помощью PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1aa14-140">If you need to change the default domain after your Bookings mailbox has already been created, you can do so with PowerShell:</span></span>

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

<span data-ttu-id="1aa14-141">Дополнительные сведения см. в документации по PowerShell для командлета [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="1aa14-141">For more information, see the PowerShell documentation for the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="1aa14-142">Если вы используете гибридную конфигурацию Exchange, рекомендуем тщательно проверить движение почты между локальной версией Exchange и Exchange Online при изменении домена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1aa14-142">If you are using an Exchange hybrid configuration, we recommend that you thoroughly test mail flow between on-premises Exchange and Exchange Online when changing the default domain.</span></span>

## <a name="sending-feedback"></a><span data-ttu-id="1aa14-143">Отправка отзывов</span><span class="sxs-lookup"><span data-stu-id="1aa14-143">Sending feedback</span></span>

<span data-ttu-id="1aa14-144">Отзывы можно отправлять по адресу:</span><span class="sxs-lookup"><span data-stu-id="1aa14-144">We welcome your feedback on:</span></span>

  - <span data-ttu-id="1aa14-145">Впечатления от использования или удобство использования</span><span class="sxs-lookup"><span data-stu-id="1aa14-145">User experience or ease of use</span></span>
  - <span data-ttu-id="1aa14-146">Пробелы в функциях или отсутствие функций</span><span class="sxs-lookup"><span data-stu-id="1aa14-146">Feature gaps or missing functionality</span></span>
  - <span data-ttu-id="1aa14-147">Дефекты и проблемы</span><span class="sxs-lookup"><span data-stu-id="1aa14-147">Bugs or issues</span></span>
  
<span data-ttu-id="1aa14-148">Чтобы отправить сообщение, для **ВСЕХ** проблем нажмите кнопку **Справка** в нижней части левой панели навигации Teams, а затем **Сообщить о проблеме**.</span><span class="sxs-lookup"><span data-stu-id="1aa14-148">To send feedback, click the **Help** button near the bottom of the Teams left navigation bar, then click **Report a Problem** for **ALL** issues.</span></span> <span data-ttu-id="1aa14-149">В самом начале отзыва просим указать, что это отзыв по приложению Bookings - тогда мы сможем легко отличать сообщения, касающиеся приложения Bookings.</span><span class="sxs-lookup"><span data-stu-id="1aa14-149">Please note at the beginning of your feedback report that you are sending feedback about "Bookings" so we can easily identify Bookings issues.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1aa14-150">Родственные темы</span><span class="sxs-lookup"><span data-stu-id="1aa14-150">Related topics</span></span>

<span data-ttu-id="1aa14-151">
  [Документация по Bookings для конечных пользователей](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)</span><span class="sxs-lookup"><span data-stu-id="1aa14-151">[Bookings documentation for end users](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)</span></span>
