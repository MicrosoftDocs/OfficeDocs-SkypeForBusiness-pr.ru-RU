---
title: Создание новой или редактирование существующей неназначенный номер телефона
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: Неназначенные номера — это телефонные номера, допустимые для вашей организации, но не назначенные пользователю или телефону. В таблице неназначенных номеров указывается, как обрабатываются такие номера.
ms.openlocfilehash: 176e1b0485b9fc9584b770e4708cad0bf0662e00
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32221347"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="b8ec2-104">Неназначенный номер телефона: создание нового или редактирование существующего</span><span class="sxs-lookup"><span data-stu-id="b8ec2-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

> [!NOTE]
> <span data-ttu-id="b8ec2-105">Exchange единой системы обмена СООБЩЕНИЯМИ остается доступным в Скайп для Business Server 2019 при Скайп для бизнеса 2019 интеграции с Exchange 2013 или Exchange 2016.</span><span class="sxs-lookup"><span data-stu-id="b8ec2-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="b8ec2-106">Из-за изменения в поддержке в Exchange 2019 интеграции с Exchange единой системы обмена СООБЩЕНИЯМИ, отзыва emphasised пользу функции голосовой почты в облаке и облачных автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="b8ec2-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasised in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="b8ec2-p103">Неназначенные номера — это телефонные номера, допустимые для вашей организации, но не назначенные пользователю или телефону. В таблице неназначенных номеров указывается, как обрабатываются такие номера.</span><span class="sxs-lookup"><span data-stu-id="b8ec2-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8ec2-109">Завершив создание новый диапазон неназначенных номеров или редактирование существующего, нажмите **кнопку ОК** , чтобы вернуться на страницу **Неназначенный номер** , где перечислены все диапазоны номеров.</span><span class="sxs-lookup"><span data-stu-id="b8ec2-109">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges.</span></span> <span data-ttu-id="b8ec2-110">Изменения, внесенные на странице **New Unassigned номер диапазона** или **Изменение Rage неназначенный номер** страницы не передаются базу данных только после нажатия кнопки **Сохранить все** на странице **Неназначенный номер** .</span><span class="sxs-lookup"><span data-stu-id="b8ec2-110">The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="b8ec2-111">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="b8ec2-111">UI Reference</span></span>

<span data-ttu-id="b8ec2-112">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="b8ec2-112">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="b8ec2-113">**Имя** Введите описательное имя, которое определяет диапазон неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="b8ec2-113">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="b8ec2-114">После сохранения диапазон, это имя нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="b8ec2-114">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="b8ec2-115">**Номер диапазона** В первом поле введите первый номер диапазона неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="b8ec2-115">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="b8ec2-116">Во втором поле введите последний номер диапазона.</span><span class="sxs-lookup"><span data-stu-id="b8ec2-116">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="b8ec2-117">Первый номер диапазона должен быть меньше или равен последнему номеру диапазона.</span><span class="sxs-lookup"><span data-stu-id="b8ec2-117">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="b8ec2-118">Если первый номер или последний номер диапазона содержит добавочный номер, то оба номера (первый и последний) должны содержать добавочный номер. Кроме того, добавочный номер должен быть одинаковым для первого и последнего номера диапазона.</span><span class="sxs-lookup"><span data-stu-id="b8ec2-118">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="b8ec2-119">Номер должен соответствовать регулярному выражению (tel:) ? (\+) ? [1-9] \d{0,17}(; ext = [1-9] \d{0,9}) ?.</span><span class="sxs-lookup"><span data-stu-id="b8ec2-119">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="b8ec2-120">Это означает, что номер может начинаться с строка tel: (если не указать эту строку он автоматически добавляется автоматически), знак плюс (+), а цифры от 1 до 9.</span><span class="sxs-lookup"><span data-stu-id="b8ec2-120">This means the number may begin with the string tel: (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="b8ec2-121">Номер телефона может быть длиной до 17 цифр, и в конце может быть указан добавочный номер в формате ";ext=добавочный_номер".</span><span class="sxs-lookup"><span data-stu-id="b8ec2-121">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="b8ec2-122">**Служба оповещения** Выберите **оповещение** , приложение объявлений обработки входящих звонков или **Exchange единой системы обмена СООБЩЕНИЯМИ** для Exchange единой системы обмена СООБЩЕНИЯМИ автосекретарь обработки входящих звонков.</span><span class="sxs-lookup"><span data-stu-id="b8ec2-122">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="b8ec2-123">Если вы выбрали **оповещение** для **службы оповещения**:</span><span class="sxs-lookup"><span data-stu-id="b8ec2-123">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="b8ec2-124">**Полное доменное имя конечного сервера** Выберите идентификатор службы службы приложения, на котором выполняется приложение оповещения, который будет обрабатывать входящие звонки для этого диапазона неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="b8ec2-124">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="b8ec2-125">**Оповещения** Выберите извещение, воспроизводимое для этого диапазона неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="b8ec2-125">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

- <span data-ttu-id="b8ec2-126">Если вы выбрали **Exchange единой системы обмена СООБЩЕНИЯМИ** для **службы оповещения**:</span><span class="sxs-lookup"><span data-stu-id="b8ec2-126">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="b8ec2-127">**Телефонный номер автосекретаря** Выберите номер телефона для единой системы обмена СООБЩЕНИЯМИ автосекретаря Exchange.</span><span class="sxs-lookup"><span data-stu-id="b8ec2-127">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="b8ec2-128">Для получения дополнительных сведений о объявления функций и возможностей см [в приложении объявлений в Скайп для бизнеса](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="b8ec2-128">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="b8ec2-129">Дополнительные сведения о работе с диапазонами неназначенных номеров см. в разделе [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="b8ec2-129">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


