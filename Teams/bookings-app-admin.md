---
title: Виртуальные посещения в Microsoft Teams и приложении "резервирование"
author: msdmaguire
ms.author: dmaguire
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
ms.reviewer: ''
description: Microsoft Teams и виртуальные посещения с помощью приложения "резервирование"
ms.openlocfilehash: 0c88feec8a90b2794e93fb9c51bffafabf942748
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766962"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a><span data-ttu-id="8623f-103">Виртуальные посещения в Microsoft Teams и приложении "резервирование"</span><span class="sxs-lookup"><span data-stu-id="8623f-103">Virtual visits with Microsoft Teams and the Bookings app</span></span>

<span data-ttu-id="8623f-104">Приложение "резервирование" в Microsoft Teams предоставляет простой способ планирования в личных и виртуальных встречах, например посещения учреждений, финансовых consultations, интервью, обслуживания клиентов, рабочих часов в офисном офисе и т. д.</span><span class="sxs-lookup"><span data-stu-id="8623f-104">The Bookings app in Microsoft Teams offers a simple way to schedule in-person and virtual appointments, such as healthcare visits, financial consultations, interviews, customer support, education office hours, and much more.</span></span>

<span data-ttu-id="8623f-105">Планировщики могут управлять несколькими календарями отдела и сотрудников, а также общением с внутренними и внешними участниками из одной функции.</span><span class="sxs-lookup"><span data-stu-id="8623f-105">Schedulers can manage multiple department and staff calendars, as well as communications with internal and external attendees, from a single experience.</span></span> <span data-ttu-id="8623f-106">Виртуальные встречи сами по себе сохраняются с помощью собраний Microsoft Teams, предлагающих широкие возможности видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="8623f-106">The virtual appointments themselves are held via Microsoft Teams Meetings, which offers robust videoconferencing capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="8623f-107">Только планировщикам необходимо, чтобы в Teams было установлено приложение "резервирование".</span><span class="sxs-lookup"><span data-stu-id="8623f-107">Only schedulers need to have the Bookings app installed in Teams.</span></span> <span data-ttu-id="8623f-108">Для сотрудников, испроизводящих участие в виртуальных встречах, это приложение не требуется.</span><span class="sxs-lookup"><span data-stu-id="8623f-108">Staff conducting or participating in virtual appointments do not need the app.</span></span> <span data-ttu-id="8623f-109">Они могут просто присоединиться к встречам из календаря Outlook или Teams или из ссылки в сообщении с подтверждением их резервирования.</span><span class="sxs-lookup"><span data-stu-id="8623f-109">They can simply join appointments from their Outlook or Teams calendar or from a link in their booking confirmation email.</span></span>

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a><span data-ttu-id="8623f-110">Предварительные требования для использования приложения "резервирование" в Teams</span><span class="sxs-lookup"><span data-stu-id="8623f-110">Prerequisites for using the Bookings app in Teams</span></span>

- <span data-ttu-id="8623f-111">Почтовый ящик Exchange должен находиться в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8623f-111">The Exchange mailbox must be in Exchange Online.</span></span> <span data-ttu-id="8623f-112">Локальные почтовые ящики Exchange Server не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="8623f-112">On-premises Exchange Server mailboxes are not supported.</span></span>

- <span data-ttu-id="8623f-113">Для организации должны быть включены книги Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8623f-113">Microsoft Bookings must be turned on for the organization.</span></span>

- <span data-ttu-id="8623f-114">У пользователей должна быть соответствующая лицензия.</span><span class="sxs-lookup"><span data-stu-id="8623f-114">Users must have an appropriate license.</span></span> <span data-ttu-id="8623f-115">Office 365 a3, A5, E3 и 3, а также в Microsoft 365 Business Standard,, A3, A5, E3 и 3.</span><span class="sxs-lookup"><span data-stu-id="8623f-115">Office 365 A3, A5, E3, and E5, as well as Microsoft 365 Business Standard, A3, A5, E3, and E5 are supported.</span></span>

- <span data-ttu-id="8623f-116">Для всех пользователей приложения "резервирование" и всех участников, участвующих в собраниях, должна быть лицензия, поддерживающая Планирование собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="8623f-116">All users of the Bookings app and all staff participating in meetings must have a license that supports Teams Meeting scheduling.</span></span>

- <span data-ttu-id="8623f-117">Ваши системы должны соответствовать всем требованиям к [программному обеспечению и браузеру](hardware-requirements-for-the-teams-app.md).</span><span class="sxs-lookup"><span data-stu-id="8623f-117">Your systems must meet all [Software and browser prerequisites](hardware-requirements-for-the-teams-app.md).</span></span>

## <a name="availability-of-bookings-in-teams"></a><span data-ttu-id="8623f-118">Доступность резервирований в Teams</span><span class="sxs-lookup"><span data-stu-id="8623f-118">Availability of Bookings in Teams</span></span>

<span data-ttu-id="8623f-119">Приложение "книги Microsoft для Teams" доступно на рабочем столе и в Интернете.</span><span class="sxs-lookup"><span data-stu-id="8623f-119">Microsoft Bookings App for Teams is available on the desktop and web.</span></span> <span data-ttu-id="8623f-120">Его можно найти в разделе [приложения в Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) и в разделе **Управление приложениями** в центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="8623f-120">It can be found under [Apps within Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) and under **Manage Apps** within Teams Admin Center.</span></span>

### <a name="control-access-to-bookings-within-your-organization"></a><span data-ttu-id="8623f-121">Управление доступом к книгам в Организации</span><span class="sxs-lookup"><span data-stu-id="8623f-121">Control access to Bookings within your organization</span></span>

<span data-ttu-id="8623f-122">Есть несколько способов управления доступом пользователей к приложению "резервирование" и определенными функциями приложения.</span><span class="sxs-lookup"><span data-stu-id="8623f-122">There are several ways to control who has access to the Bookings app and to specific features of the app.</span></span> <span data-ttu-id="8623f-123">Сведения о том, как включать и отключать Microsoft Books в центре администрирования Microsoft 365, а также о том, как создавать политики приложений для создания книг, чтобы разрешить выбранным пользователям создавать календари книги, можно узнать в [статье получение доступа к книгам Microsoft](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span><span class="sxs-lookup"><span data-stu-id="8623f-123">To learn how to turn Microsoft Bookings on or off in the Microsoft 365 admin center, as well as how to create a Bookings app policy to allow selected users to create Bookings calendars, see [Get access to Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span></span> <span data-ttu-id="8623f-124">Вы также можете ознакомиться со сведениями о том, как [создать политику приложений Teams, чтобы закрепить приложение "книги" для выбора пользователей](teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8623f-124">You can also learn how to [Create a Teams app policy to pin the Bookings app for select users](teams-app-setup-policies.md).</span></span>

## <a name="recommended-meeting-policy-settings"></a><span data-ttu-id="8623f-125">Рекомендуемые параметры политики собраний</span><span class="sxs-lookup"><span data-stu-id="8623f-125">Recommended Meeting Policy Settings</span></span>

<span data-ttu-id="8623f-126">Для обеспечения оптимальной работы при резервировании создайте политику собраний для сотрудников, чтобы автоматически допустить **всех сотрудников вашей организации** .</span><span class="sxs-lookup"><span data-stu-id="8623f-126">To enable the best experience for Bookings, create a staff meeting policy to automatically admit **Everyone in your organization** .</span></span> <span data-ttu-id="8623f-127">Это позволит сотрудникам автоматически присоединиться к встрече и включить в него сведения о зале обслуживания внешних участников.</span><span class="sxs-lookup"><span data-stu-id="8623f-127">This will allow staff to join the appointment automatically and enable lobby experience for external attendees.</span></span> <span data-ttu-id="8623f-128">Вы можете узнать больше о том, как [автоматически admitting людей для собраний](meeting-policies-in-teams.md#automatically-admit-people).</span><span class="sxs-lookup"><span data-stu-id="8623f-128">You can learn more about [automatically admitting people to meetings](meeting-policies-in-teams.md#automatically-admit-people).</span></span>

### <a name="optional-staff-approvals-setting"></a><span data-ttu-id="8623f-129">Необязательные параметры утверждений сотрудников</span><span class="sxs-lookup"><span data-stu-id="8623f-129">Optional staff approvals setting</span></span>

<span data-ttu-id="8623f-130">В качестве дополнительного параметра конфиденциальности вы можете выбрать требование предоставления сотрудникам прав на предоставление доступа к сведениям о доступности в расписании с помощью резервирования и до того, как они могут быть зарезервированы для встречи.</span><span class="sxs-lookup"><span data-stu-id="8623f-130">As an extra privacy setting, you can choose to require staff to opt in before their schedule availability information is shared through Bookings and before they can be booked for an appointment.</span></span>  

<span data-ttu-id="8623f-131">Чтобы включить этот параметр, перейдите в раздел Параметры параметров **центра администрирования Microsoft 365** \> **Settings** \> **Settings** и выберите пункт **резервирования** .</span><span class="sxs-lookup"><span data-stu-id="8623f-131">To enable this setting, go to **Microsoft 365 admin center** \> **Settings** \> **Settings** , then select **Bookings** .</span></span>

<span data-ttu-id="8623f-132">Если этот параметр включен, сотрудники получат сообщение электронной почты, в котором они просят подтвердить участие в календаре резервирования.</span><span class="sxs-lookup"><span data-stu-id="8623f-132">With this setting turned on, staff will receive an email in which they are asked to approve membership to a booking calendar.</span></span>  

<span data-ttu-id="8623f-133">Эта функция постепенно размещается для пользователей Microsoft 365 и Office 365 на всех языках.</span><span class="sxs-lookup"><span data-stu-id="8623f-133">This feature is gradually being rolled out worldwide to Microsoft 365 and Office 365 customers.</span></span> <span data-ttu-id="8623f-134">Если все варианты пока недоступны в вашей среде, вернитесь в ближайшее время.</span><span class="sxs-lookup"><span data-stu-id="8623f-134">If all options are not yet available in your environment, check back soon.</span></span>

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a><span data-ttu-id="8623f-135">Изменение домена по умолчанию при настройке почтовых ящиков для резервирования</span><span class="sxs-lookup"><span data-stu-id="8623f-135">Changing your default domain when setting up Bookings mailboxes</span></span>

<span data-ttu-id="8623f-136">При настройке почтового ящика архивации используется домен электронной почты по умолчанию для Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="8623f-136">When setting up a Bookings mailbox, the default email domain of your Microsoft 365 or Office 365 organization is used.</span></span> <span data-ttu-id="8623f-137">Однако это может привести к возникновению проблем при отправке приглашений на собрания внешним получателям. Ваше приглашение может быть помечено как спам и перемещено в папку "Нежелательная почта", поэтому получатель может не видеть ваше приглашение.</span><span class="sxs-lookup"><span data-stu-id="8623f-137">However, this can cause problems when sending meeting invites to external recipients; your invite might be flagged as spam and moved to the recipient’s junk folder, so the recipient might never see your invite.</span></span>

<span data-ttu-id="8623f-138">Рекомендуется изменить домен, используемый по умолчанию, перед созданием почтового ящика книги.</span><span class="sxs-lookup"><span data-stu-id="8623f-138">We recommend that you change the default domain prior to creating your Bookings mailbox.</span></span> <span data-ttu-id="8623f-139">Сведения о том, как это сделать, можно найти в разделе " [вопросы и ответы](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)" для доменов.</span><span class="sxs-lookup"><span data-stu-id="8623f-139">For information on how to do this, see the [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span></span>

<span data-ttu-id="8623f-140">Если вы хотите изменить домен по умолчанию после того, как почтовый ящик книги уже создан, вы можете сделать это с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8623f-140">If you need to change the default domain after your Bookings mailbox has already been created, you can do so with PowerShell:</span></span>

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

<span data-ttu-id="8623f-141">Дополнительные сведения можно найти в документации по PowerShell для командлета [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) .</span><span class="sxs-lookup"><span data-stu-id="8623f-141">For more information, see the PowerShell documentation for the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="8623f-142">При использовании гибридной конфигурации Exchange рекомендуется тщательно протестировать поток обработки почты между локальным сервером Exchange и Exchange Online при изменении домена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8623f-142">If you are using an Exchange hybrid configuration, we recommend that you thoroughly test mail flow between on-premises Exchange and Exchange Online when changing the default domain.</span></span>

## <a name="sending-feedback"></a><span data-ttu-id="8623f-143">Отправка отзыва</span><span class="sxs-lookup"><span data-stu-id="8623f-143">Sending feedback</span></span>

<span data-ttu-id="8623f-144">Мы рады вашим отзывам:</span><span class="sxs-lookup"><span data-stu-id="8623f-144">We welcome your feedback on:</span></span>

  - <span data-ttu-id="8623f-145">Взаимодействие с пользователем и простота использования</span><span class="sxs-lookup"><span data-stu-id="8623f-145">User experience or ease of use</span></span>
  - <span data-ttu-id="8623f-146">Функции, пропуски и отсутствующие функциональные возможности</span><span class="sxs-lookup"><span data-stu-id="8623f-146">Feature gaps or missing functionality</span></span>
  - <span data-ttu-id="8623f-147">Ошибки или проблемы</span><span class="sxs-lookup"><span data-stu-id="8623f-147">Bugs or issues</span></span>
  
<span data-ttu-id="8623f-148">Чтобы отправить отзыв, нажмите кнопку **Справка** в нижней части панели навигации слева для групп, а затем выберите **сообщить о проблеме** для **всех** проблем.</span><span class="sxs-lookup"><span data-stu-id="8623f-148">To send feedback, click the **Help** button near the bottom of the Teams left navigation bar, then click **Report a Problem** for **ALL** issues.</span></span> <span data-ttu-id="8623f-149">Обратите внимание на то, что в начале вашего отчета о отзывах вы отправляете отзыв о том, что вы можете легко выявить проблемы с зарезервированными книгами.</span><span class="sxs-lookup"><span data-stu-id="8623f-149">Please note at the beginning of your feedback report that you are sending feedback about "Bookings" so we can easily identify Bookings issues.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8623f-150">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8623f-150">Related topics</span></span>

[<span data-ttu-id="8623f-151">Документация по книгам для конечных пользователей</span><span class="sxs-lookup"><span data-stu-id="8623f-151">Bookings documentation for end users</span></span>](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
