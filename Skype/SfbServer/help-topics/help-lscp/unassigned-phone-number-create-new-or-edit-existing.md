---
title: Неназначенный номер телефона создание нового или изменение существующего
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: Неназначенные номера — это телефонные номера, допустимые для вашей организации, но не назначенные пользователю или телефону. В таблице неназначенных номеров указывается, как обрабатываются такие номера.
ms.openlocfilehash: e8a294273591969430abbbc450a37a5292fbe0c1
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685672"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="7cac2-104">Неназначенный номер телефона: создание нового или редактирование существующего</span><span class="sxs-lookup"><span data-stu-id="7cac2-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

<span data-ttu-id="7cac2-p102">Неназначенные номера — это телефонные номера, допустимые для вашей организации, но не назначенные пользователю или телефону. В таблице неназначенных номеров указывается, как обрабатываются такие номера.</span><span class="sxs-lookup"><span data-stu-id="7cac2-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7cac2-107">После того как вы завершите создание нового неназначенного диапазона номеров или редактируете существующий, нажмите кнопку **ОК** , чтобы вернуться на страницу **неназначенный номер** , на которой перечислены все диапазоны номеров.</span><span class="sxs-lookup"><span data-stu-id="7cac2-107">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges.</span></span> <span data-ttu-id="7cac2-108">Изменения, внесенные на странице " **новый диапазон неназначенных номеров** " или " **изменить неназначенный номер** ", не фиксируются в базе данных, пока вы не нажимайте кнопку " **сохранить все** " на странице " **неназначенные номера** ".</span><span class="sxs-lookup"><span data-stu-id="7cac2-108">The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="7cac2-109">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="7cac2-109">UI Reference</span></span>

<span data-ttu-id="7cac2-110">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="7cac2-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="7cac2-111">**Name (имя** ) Введите описательное имя, определяющее неназначенный диапазон номеров.</span><span class="sxs-lookup"><span data-stu-id="7cac2-111">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="7cac2-112">После сохранения диапазона это имя изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="7cac2-112">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="7cac2-113">**Диапазон номеров** В первом поле введите начальный номер неназначенного диапазона номеров.</span><span class="sxs-lookup"><span data-stu-id="7cac2-113">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="7cac2-114">Во втором поле Введите конечный номер диапазона.</span><span class="sxs-lookup"><span data-stu-id="7cac2-114">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="7cac2-115">Первый номер диапазона должен быть меньше или равен последнему номеру диапазона.</span><span class="sxs-lookup"><span data-stu-id="7cac2-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="7cac2-116">Если первый номер или последний номер диапазона содержит добавочный номер, то оба номера (первый и последний) должны содержать добавочный номер. Кроме того, добавочный номер должен быть одинаковым для первого и последнего номера диапазона.</span><span class="sxs-lookup"><span data-stu-id="7cac2-116">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="7cac2-117">Номер должен соответствовать регулярному выражению (Tel:) ( \+)? [1-9] \d{0,17}(; ext = [1-9] \d{0,9})?.</span><span class="sxs-lookup"><span data-stu-id="7cac2-117">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="7cac2-118">Это означает, что номер может начинаться со строки Tel: (если вы не укажете, что она будет автоматически добавлена для вас), знак "плюс" (+) и цифра 1 – 9.</span><span class="sxs-lookup"><span data-stu-id="7cac2-118">This means the number may begin with the string tel: (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="7cac2-119">Номер телефона может быть длиной до 17 цифр, и в конце может быть указан добавочный номер в формате ";ext=добавочный_номер".</span><span class="sxs-lookup"><span data-stu-id="7cac2-119">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="7cac2-120">**Служба объявлений** Нажмите кнопку **извещение** , чтобы приложение извещения обрабатывало входящий звонок или **UM Exchange** , чтобы автосекретарь Exchange UM обрабатывал входящий звонок.</span><span class="sxs-lookup"><span data-stu-id="7cac2-120">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="7cac2-121">Если вы выбрали службу **извещения** для **объявлений**, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="7cac2-121">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="7cac2-122">**Полное доменное имя конечного сервера** Выберите идентификатор службы приложения, который запускает приложение объявлений, которое будет обрабатывать входящие звонки в этот диапазон неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="7cac2-122">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="7cac2-123">**Объявление** Выберите извещение для воспроизведения по этому диапазону неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="7cac2-123">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

- <span data-ttu-id="7cac2-124">Если вы выбрали службу **сообщений Exchange** для **службы объявлений**, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="7cac2-124">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="7cac2-125">**Номер телефона для автосекретаря** Выберите номер телефона автоматического секретаря UM Exchange.</span><span class="sxs-lookup"><span data-stu-id="7cac2-125">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="7cac2-126">Дополнительные сведения о функциях и возможностях объявлений вы увидите [в разделе Планирование приложения для объявлений в Skype для бизнеса 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="7cac2-126">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="7cac2-127">Дополнительные сведения о работе с диапазонами неназначенных номеров см. в разделе [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="7cac2-127">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


