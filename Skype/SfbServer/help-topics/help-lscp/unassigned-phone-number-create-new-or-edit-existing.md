---
title: Неназваный номер телефона Создать новый или изменить существующие
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: Неназначенные номера — это телефонные номера, допустимые для вашей организации, но не назначенные пользователю или телефону. В таблице неназначенных номеров указывается, как обрабатываются такие номера.
ms.openlocfilehash: 51c3f640bd9d98bcda9d5dd69406461e9c8393fd
ms.sourcegitcommit: c477aa1a7da0b6b9bea1f5d10f1395eef418bfdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711746"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="79825-104">Неназначенный номер телефона: создание нового или редактирование существующего</span><span class="sxs-lookup"><span data-stu-id="79825-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

<span data-ttu-id="79825-p102">Неназначенные номера — это телефонные номера, допустимые для вашей организации, но не назначенные пользователю или телефону. В таблице неназначенных номеров указывается, как обрабатываются такие номера.</span><span class="sxs-lookup"><span data-stu-id="79825-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79825-p103">Когда вы закончите создавать новый или изменять существующий диапазон неназначенных номеров, нажмите кнопку **ОК**, чтобы вернуться на страницу **Неназначенный номер** со списком всех диапазонов номеров. Изменения, внесенные вами на странице **Создание диапазона неназначенных номеров** или **Изменение диапазона неназначенных номеров**, не сохраняются в базе данных до тех пор, пока вы не нажмете кнопку **Сохранить все** на странице **Неназначенный номер**.</span><span class="sxs-lookup"><span data-stu-id="79825-p103">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges. The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="79825-109">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="79825-109">UI Reference</span></span>

<span data-ttu-id="79825-110">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="79825-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="79825-111">**Имя** Введите описательное имя, указывательное на диапазон неназвинных номеров.</span><span class="sxs-lookup"><span data-stu-id="79825-111">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="79825-112">После сохранения диапазона это имя не может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="79825-112">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="79825-113">**Диапазон номеров** В первом поле введите начальское число ненаназшенного диапазона номеров.</span><span class="sxs-lookup"><span data-stu-id="79825-113">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="79825-114">Во втором поле введите конечное число диапазона.</span><span class="sxs-lookup"><span data-stu-id="79825-114">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="79825-115">Начальный номер диапазона должен быть меньше или равен конечному номеру диапазона.</span><span class="sxs-lookup"><span data-stu-id="79825-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="79825-116">Если начальный или конечный номер диапазона содержит добавочный номер, то и начальный, и конечный номера диапазона должны содержать добавочный номер, который должен быть одинаковым для обоих номеров.</span><span class="sxs-lookup"><span data-stu-id="79825-116">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="79825-117">Номер должен соответствовать регулярному `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?` выражению.</span><span class="sxs-lookup"><span data-stu-id="79825-117">The number must match the regular expression `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?`.</span></span> <span data-ttu-id="79825-118">Это означает, что номер может начинаться со строки (если вы не указываете, что строка будет автоматически добавлена для вас), знак плюс (+) и цифру `tel:` 1-9.</span><span class="sxs-lookup"><span data-stu-id="79825-118">This means the number may begin with the string `tel:` (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="79825-119">Номер телефона может быть длиной до 17 цифр, и в конце может быть указан добавочный номер в формате ";ext=добавочный_номер".</span><span class="sxs-lookup"><span data-stu-id="79825-119">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="79825-120">**Служба объявлений** Выберите **Объявление,** чтобы приложение Announcement обрабатывал входящий вызов или **exchange UM,** чтобы иметь автосекретарь обмена данными для обработки входящих вызовов.</span><span class="sxs-lookup"><span data-stu-id="79825-120">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="79825-121">Если вы выбрали для параметра **Служба извещения** значение **Извещение**:</span><span class="sxs-lookup"><span data-stu-id="79825-121">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="79825-122">**FQDN сервера назначения** Выберите номер службы приложения, которое запускает приложение Announcement, которое будет обрабатывать входящие вызовы в этот диапазон ненаназранных номеров.</span><span class="sxs-lookup"><span data-stu-id="79825-122">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="79825-123">**Объявление** Выберите объявление для этого диапазона неназранных номеров.</span><span class="sxs-lookup"><span data-stu-id="79825-123">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

- <span data-ttu-id="79825-124">Если вы выбрали для параметра **Служба извещения** значение **Единая система обмена сообщениями Exchange**:</span><span class="sxs-lookup"><span data-stu-id="79825-124">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="79825-125">**автосекретарь номер телефона** Выберите номер телефона для обмена автосекретарь.</span><span class="sxs-lookup"><span data-stu-id="79825-125">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="79825-126">Подробные сведения о возможностях и возможностях объявления см. в документации По планированию в [Skype for Business 2015.](../../plan-your-deployment/enterprise-voice-solution/announcement.md)</span><span class="sxs-lookup"><span data-stu-id="79825-126">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="79825-127">Дополнительные сведения о работе с диапазонами неназначенных номеров см. в разделе [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) в документации по применению.</span><span class="sxs-lookup"><span data-stu-id="79825-127">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


