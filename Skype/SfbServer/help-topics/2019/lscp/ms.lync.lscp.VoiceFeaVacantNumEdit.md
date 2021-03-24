---
title: Неназваный номер телефона Создать новый или изменить существующие
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: Неназначенные номера — это телефонные номера, допустимые для вашей организации, но не назначенные пользователю или телефону. В таблице неназначенных номеров указывается, как обрабатываются такие номера.
ms.openlocfilehash: 49837269f81eaee09a0c191008234345d1d6d19f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097055"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="da7ac-104">Неназначенный номер телефона: создание нового или редактирование существующего</span><span class="sxs-lookup"><span data-stu-id="da7ac-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

> [!NOTE]
> <span data-ttu-id="da7ac-105">При интеграции Skype for Business Server 2019 с Exchange 2013 или Exchange 2016 skype for Business 2019 остается доступной в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="da7ac-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="da7ac-106">Из-за изменений в поддержке в Exchange 2019 интеграция exchange um отозвучит в пользу функций облачной голосовой почты и облачных автосекретарь.</span><span class="sxs-lookup"><span data-stu-id="da7ac-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="da7ac-p103">Неназначенные номера — это телефонные номера, допустимые для вашей организации, но не назначенные пользователю или телефону. В таблице неназначенных номеров указывается, как обрабатываются такие номера.</span><span class="sxs-lookup"><span data-stu-id="da7ac-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="da7ac-p104">Когда вы закончите создавать новый или изменять существующий диапазон неназначенных номеров, нажмите кнопку **ОК**, чтобы вернуться на страницу **Неназначенный номер** со списком всех диапазонов номеров. Изменения, внесенные вами на странице **Создание диапазона неназначенных номеров** или **Изменение диапазона неназначенных номеров**, не сохраняются в базе данных до тех пор, пока вы не нажмете кнопку **Сохранить все** на странице **Неназначенный номер**.</span><span class="sxs-lookup"><span data-stu-id="da7ac-p104">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges. The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="da7ac-111">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="da7ac-111">UI Reference</span></span>

<span data-ttu-id="da7ac-112">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="da7ac-112">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="da7ac-113">**Имя** Введите описательное имя, указывательное на диапазон неназвинных номеров.</span><span class="sxs-lookup"><span data-stu-id="da7ac-113">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="da7ac-114">После сохранения диапазона это имя не может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="da7ac-114">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="da7ac-115">**Диапазон номеров** В первом поле введите начальское число ненаназшенного диапазона номеров.</span><span class="sxs-lookup"><span data-stu-id="da7ac-115">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="da7ac-116">Во втором поле введите конечное число диапазона.</span><span class="sxs-lookup"><span data-stu-id="da7ac-116">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="da7ac-117">Начальный номер диапазона должен быть меньше или равен конечному номеру диапазона.</span><span class="sxs-lookup"><span data-stu-id="da7ac-117">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="da7ac-118">Если начальный или конечный номер диапазона содержит добавочный номер, то и начальный, и конечный номера диапазона должны содержать добавочный номер, который должен быть одинаковым для обоих номеров.</span><span class="sxs-lookup"><span data-stu-id="da7ac-118">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="da7ac-119">Номер должен соответствовать регулярному выражению `tel:` \+ ()?()? [1-9]\d {0,17} (;ext=[1-9]\d)?. {0,9}</span><span class="sxs-lookup"><span data-stu-id="da7ac-119">The number must match the regular expression (`tel:`)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="da7ac-120">Это означает, что номер может начинаться со строки "tel:".</span><span class="sxs-lookup"><span data-stu-id="da7ac-120">This means the number may begin with the string 'tel:'.</span></span> <span data-ttu-id="da7ac-121">Если вы не указываете эту строку, она будет автоматически добавлена для вас, например знак плюс (+) и цифру от 1 до 9.</span><span class="sxs-lookup"><span data-stu-id="da7ac-121">If you don't specify that string, it will be automatically added for you, such as a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="da7ac-122">Номер телефона может быть длиной до 17 цифр, и в конце может быть указан добавочный номер в формате ";ext=добавочный_номер".</span><span class="sxs-lookup"><span data-stu-id="da7ac-122">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="da7ac-123">**Служба объявлений** Выберите **Объявление,** чтобы приложение Announcement обрабатывал входящий вызов или **exchange UM,** чтобы иметь автосекретарь обмена данными для обработки входящих вызовов.</span><span class="sxs-lookup"><span data-stu-id="da7ac-123">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="da7ac-124">Если вы выбрали для параметра **Служба извещения** значение **Извещение**:</span><span class="sxs-lookup"><span data-stu-id="da7ac-124">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="da7ac-125">**FQDN сервера назначения** Выберите номер службы приложения, которое запускает приложение Announcement, которое будет обрабатывать входящие вызовы в этот диапазон ненаназранных номеров.</span><span class="sxs-lookup"><span data-stu-id="da7ac-125">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="da7ac-126">**Объявление** Выберите объявление для этого диапазона неназранных номеров.</span><span class="sxs-lookup"><span data-stu-id="da7ac-126">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

- <span data-ttu-id="da7ac-127">Если вы выбрали для параметра **Служба извещения** значение **Единая система обмена сообщениями Exchange**:</span><span class="sxs-lookup"><span data-stu-id="da7ac-127">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="da7ac-128">**автосекретарь номер телефона** Выберите номер телефона для обмена автосекретарь.</span><span class="sxs-lookup"><span data-stu-id="da7ac-128">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="da7ac-129">Подробные сведения о возможностях и возможностях объявления см. в документации По планированию в Skype для бизнеса Plan [for the Announcement](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) application.</span><span class="sxs-lookup"><span data-stu-id="da7ac-129">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="da7ac-130">Дополнительные сведения о работе с диапазонами неназначенных номеров см. в разделе [Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers) в документации по применению.</span><span class="sxs-lookup"><span data-stu-id="da7ac-130">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers) in the Operations documentation.</span></span>