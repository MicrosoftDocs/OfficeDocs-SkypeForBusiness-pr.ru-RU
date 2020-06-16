---
title: Сведения о том, как отображаются фотографии пользователей в Lync
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88d6f6f6f5578994831fd15329988d963a295832
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a><span data-ttu-id="db04a-102">Сведения о том, как отображаются фотографии пользователей в Lync</span><span class="sxs-lookup"><span data-stu-id="db04a-102">How user photos are displayed in Lync</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db04a-103">_**Последнее изменение темы:** 2014-08-25_</span><span class="sxs-lookup"><span data-stu-id="db04a-103">_**Topic Last Modified:** 2014-08-25_</span></span>

<span data-ttu-id="db04a-104">**Сводка:** Фотографии пользователей, отображаемые в клиенте Lync, могут различаться в зависимости от того, какой компонент Lync используется, например в конференц-зале или чат-сеансе обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="db04a-104">**Summary:** User photos displayed in Lync client can be different depending on which Lync feature you are using, such as when in a conference or an IM chat.</span></span>

<span data-ttu-id="db04a-105">Lync 2010 представил возможность включить фотографию с профилем Lync, отображаемую для других пользователей Lync.</span><span class="sxs-lookup"><span data-stu-id="db04a-105">Lync 2010 introduced the ability to include a photo with your Lync profile that is displayed to other Lync users.</span></span> <span data-ttu-id="db04a-106">Вы также можете выбрать, следует ли отображать фотографии для контактов в клиенте Lync.</span><span class="sxs-lookup"><span data-stu-id="db04a-106">You can also choose whether or not to display photos for your contacts in Lync client.</span></span> <span data-ttu-id="db04a-107">В Lync 2013 поддерживается поддержка фотографий высокого разрешения для пользователей.</span><span class="sxs-lookup"><span data-stu-id="db04a-107">In Lync 2013, support for high-resolution photos for users.</span></span> <span data-ttu-id="db04a-108">В этом разделе описывается, как клиент Lync получает и отображает фотографии пользователей, в которых хранятся изображения, ограничения для каждого источника изображений и способы использования фотографий пользователей различными службами Lync.</span><span class="sxs-lookup"><span data-stu-id="db04a-108">This topic describes how Lync client gets and displays user photos, where the images are stored, the limitations for each image source, and how user photos are used by different Lync services.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="db04a-109">Вопросы планирования</span><span class="sxs-lookup"><span data-stu-id="db04a-109">Planning considerations</span></span>

<span data-ttu-id="db04a-110">При планировании реализации поддержки фотографий пользователей следует учитывать следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="db04a-110">You should consider the following when planning to implement support for user photos.</span></span>

  - <span data-ttu-id="db04a-111">Для поддержки фотографий пользователей высокого уровня требуется, чтобы почтовый ящик пользователя находился на сервере Exchange 2013, а учетная запись пользователя Lync — в пуле Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="db04a-111">High-definition user photo support requires that the user’s mailbox be located on Exchange 2013 and the Lync user account to be in Lync 2013 pool.</span></span>

  - <span data-ttu-id="db04a-112">Фотографии пользователей высокой четкости поддерживаются только в среде, в которой используются Lync Server 2013 и Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="db04a-112">High-definition user photos are supported only in an environment where both Lync Server 2013 and Exchange 2013 are used.</span></span>

  - <span data-ttu-id="db04a-113">Пользователи с почтовыми ящиками в Exchange 2010 всегда будут использовать атрибут **thumbnailPhoto** из доменных служб Active Directory в качестве источника фотографии пользователя.</span><span class="sxs-lookup"><span data-stu-id="db04a-113">Users with Mailboxes on Exchange 2010 will always use the **thumbnailPhoto** attribute from AD DS as the source for their user photo.</span></span>

  - <span data-ttu-id="db04a-114">Фото пользователя, сохраненное в качестве атрибута **thumbnailPhoto** из доменных служб Active Directory, не будет отображаться для внешних и Федеративных контактов.</span><span class="sxs-lookup"><span data-stu-id="db04a-114">A user photo stored as the **thumbnailPhoto** attribute from AD DS will not be displayed to external / federated contacts.</span></span>

  - <span data-ttu-id="db04a-115">Если фотографии для контактов пользователей хранятся в доменных СЛУЖБах Active Directory, размер используемого файла изображения ограничен 96 × 96 пикселей и не больше 100 КБ.</span><span class="sxs-lookup"><span data-stu-id="db04a-115">If the photos for user contacts are stored in AD DS, the image file used is limited to 96×96 pixels and no more than 100 KB file size.</span></span>

  - <span data-ttu-id="db04a-116">Если связь между Lync Server и Exchange Server потеряна, будет отображено небольшое разрешение пользователя **thumbnailPhoto** из доменных служб Active Directory и только внутренним пользователям.</span><span class="sxs-lookup"><span data-stu-id="db04a-116">If connectivity between Lync Server and Exchange Server is lost, the user’s low resolution **thumbnailPhoto** from AD DS will be displayed, and to internal users only.</span></span>

  - <span data-ttu-id="db04a-117">Фотографии пользователей с высоким разрешением отображаются в собраниях Lync 2013, когда активный динамик не поддерживает видео.</span><span class="sxs-lookup"><span data-stu-id="db04a-117">High-resolution user photos are displayed in Lync 2013 meetings when an active speaker does not have video enabled.</span></span> <span data-ttu-id="db04a-118">Кроме того, при перемещении указателя мыши на фотографию в галерее отображается фотография высокого разрешения.</span><span class="sxs-lookup"><span data-stu-id="db04a-118">Also, moving the mouse over thumbnail photo in the gallery will display the high-resolution photo.</span></span>

</div>

<div>

## <a name="user-photos-in-lync-2010"></a><span data-ttu-id="db04a-119">Фотографии пользователей в Lync 2010</span><span class="sxs-lookup"><span data-stu-id="db04a-119">User Photos in Lync 2010</span></span>

<span data-ttu-id="db04a-120">В клиенте Lync 2010 можно выбрать один из двух вариантов для отображения фотографии профиля, **корпоративного изображения по умолчанию** и **отображения рисунка с веб-адреса**.</span><span class="sxs-lookup"><span data-stu-id="db04a-120">In the Lync 2010 client, you can choose from two options to display a photo for your profile, **Default corporate picture** and **Show picture from a web address**.</span></span>

<div>

## <a name="default-corporate-picture"></a><span data-ttu-id="db04a-121">Корпоративный рисунок по умолчанию</span><span class="sxs-lookup"><span data-stu-id="db04a-121">Default corporate picture</span></span>

<span data-ttu-id="db04a-122">Если выбран параметр **Корпоративный рисунок по умолчанию** , Lync получает фотографию, отображаемую для вас из доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="db04a-122">When you choose the **Default corporate picture** option, Lync gets the photo displayed for you from Active Directory Domain Services.</span></span> <span data-ttu-id="db04a-123">Используемое изображение — это изображение, определенное как значение атрибута **thumbnailPhoto** в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="db04a-123">The image used is the image defined as the value for the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span> <span data-ttu-id="db04a-124">Это тот же файл, который используется Exchange для отображения изображений в Outlook.</span><span class="sxs-lookup"><span data-stu-id="db04a-124">This is the same file that is used by Exchange to display images in Outlook.</span></span>

<span data-ttu-id="db04a-125">Рекомендации по использованию изображений из доменных служб Active Directory включают в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="db04a-125">Considerations for using images from Active Directory Domain Services include the following:</span></span>

  - <span data-ttu-id="db04a-126">Поддерживаются только изображения с измерениями размером до 96 пикселей на 96 пикселей.</span><span class="sxs-lookup"><span data-stu-id="db04a-126">Only images with dimensions up to 96 pixels by 96 pixels are supported.</span></span> <span data-ttu-id="db04a-127">Размер файла изображения ограничен 100 КБ.</span><span class="sxs-lookup"><span data-stu-id="db04a-127">The file size for the image is limited to 100 KB.</span></span>

  - <span data-ttu-id="db04a-128">По умолчанию пользователи могут изменять изображение, используемое для атрибута **thumbnailPhoto** , хотя и не напрямую через клиент Lync.</span><span class="sxs-lookup"><span data-stu-id="db04a-128">By default, users are able to change the image used for the **thumbnailPhoto** attribute, though not directly through Lync client.</span></span> <span data-ttu-id="db04a-129">Его можно отключить с помощью доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="db04a-129">You can disable this through Active Directory Domain Services.</span></span>

  - <span data-ttu-id="db04a-130">Изображения, хранящиеся в доменных службах Active Directory, не отображаются для контактов, внешних по отношению к Организации, даже если они являются федеративными контактами.</span><span class="sxs-lookup"><span data-stu-id="db04a-130">Images stored in Active Directory Domain Services are not displayed to contacts external to your organization, even if they are federated contacts.</span></span>

  - <span data-ttu-id="db04a-131">В крупных организациях хранение и Извлечение изображений для большого числа пользователей может повлиять на размер и производительность базы данных доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="db04a-131">In large organizations, storing and retrieving the images for large numbers of users may impact the Active Directory Domain Services database size and performance.</span></span>

  - <span data-ttu-id="db04a-132">Ограниченные размеры изображения и размер файла означают, что можно использовать только изображения с небольшим разрешением.</span><span class="sxs-lookup"><span data-stu-id="db04a-132">The limited image dimensions and file size mean that only low resolution images can be used.</span></span>

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a><span data-ttu-id="db04a-133">Управление фотографиями пользователей в доменных службах Active Directory</span><span class="sxs-lookup"><span data-stu-id="db04a-133">How users manage their user photos in Active Directory Domain Services</span></span>

<span data-ttu-id="db04a-134">Пользователь не может изменить изображение, используемое в профиле доменных служб Active Directory напрямую, с помощью клиента Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="db04a-134">User cannot change the image used in their Active Directory Domain Services profile directly through Lync 2010 client.</span></span> <span data-ttu-id="db04a-135">Для этого можно использовать один из следующих параметров, если он доступен:</span><span class="sxs-lookup"><span data-stu-id="db04a-135">They can use one of the following options to do so, if available:</span></span>

  - <span data-ttu-id="db04a-136">**SharePoint Server**     Пользователи могут отправить фотографию на страницу "мой сайт" на сервере SharePoint, а затем [настроить синхронизацию профилей в SharePoint](https://go.microsoft.com/fwlink/p/?linkid=507466) , чтобы синхронизировать фотографию с атрибутом **thumbnailPhoto** в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="db04a-136">**SharePoint Server**   Users can upload a photo to ‘My Site’ on a SharePoint Server and then [configure profile synchronization in SharePoint](https://go.microsoft.com/fwlink/p/?linkid=507466) to synchronize the photo to the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="db04a-137">**Фотография, хранящаяся на общедоступном URL-адресе**     Пользователи могут настроить фотографию пользователя, указав общедоступный URL-адрес изображения, которое нужно использовать.</span><span class="sxs-lookup"><span data-stu-id="db04a-137">**Photo stored on publicly accessible URL**   Users can configure their user photo specifying a publicly accessible URL for the image that they want to use.</span></span> <span data-ttu-id="db04a-138">Изображение должно быть открыто доступным без пароля.</span><span class="sxs-lookup"><span data-stu-id="db04a-138">The image must be publicly accessible without a password.</span></span> <span data-ttu-id="db04a-139">Изображение, хранящееся в указанном веб-адресе, передается другим пользователям через категорию карточки контакта в сведениях о присутствии.</span><span class="sxs-lookup"><span data-stu-id="db04a-139">The image stored at the specified web address is transferred to other users through the contact card category in the presence information.</span></span> <span data-ttu-id="db04a-140">Когда клиент Lync должен отобразить фотографию пользователя, он получает изображение с указанного веб-адреса.</span><span class="sxs-lookup"><span data-stu-id="db04a-140">When Lync client needs to display a user photo, it retrieves the image from the specified web address.</span></span>

  - <span data-ttu-id="db04a-141">**Командлеты Exchange 2010 для Windows PowerShell**     Администраторы могут запустить командлет [Import – RecipientDataProperty](https://go.microsoft.com/fwlink/p/?linkid=507468) в командной консоли Exchange 2010, чтобы управлять атрибутом **thumbnailPhoto** .</span><span class="sxs-lookup"><span data-stu-id="db04a-141">**Exchange 2010 cmdlets for Windows PowerShell**   Administrators can run the [Import-RecipientDataProperty](https://go.microsoft.com/fwlink/p/?linkid=507468) cmdlet in the Exchange 2010 Management Shell in to manage the **thumbnailPhoto** attribute.</span></span> <span data-ttu-id="db04a-142">При импорте изображений с помощью командлетов Exchange 2010 размер файла ограничен 10 КБ.</span><span class="sxs-lookup"><span data-stu-id="db04a-142">When images are imported with Exchange 2010 cmdlets, the file size is limited to 10 KB.</span></span>

  - <span data-ttu-id="db04a-143">**Сторонние инструменты**     Пользователи могут отправлять только свои фотографии для атрибута **thumbnailPhoto** .</span><span class="sxs-lookup"><span data-stu-id="db04a-143">**Third Party tools**   Users can upload only their own photo to for the **thumbnailPhoto** attribute.</span></span>

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a><span data-ttu-id="db04a-144">Отображение изображения с веб-адреса</span><span class="sxs-lookup"><span data-stu-id="db04a-144">Show a picture from a web address</span></span>

<span data-ttu-id="db04a-145">При выборе параметра **Показать изображение с помощью веб-адреса** Lync получает изображение по указанному адресу и отображает его для фотографии пользователя в Lync.</span><span class="sxs-lookup"><span data-stu-id="db04a-145">When you choose the **Show a picture from a web address** option, Lync gets the image at the address you enter and displays it for your user photo in Lync.</span></span>

<span data-ttu-id="db04a-146">Ниже приведены рекомендации по использованию изображений из веб-адреса.</span><span class="sxs-lookup"><span data-stu-id="db04a-146">Considerations for using images from a web address include the following:</span></span>

  - <span data-ttu-id="db04a-147">Максимальные значения размера файлов определяются атрибутом **максфотосизекб** в клиентской политике, который определяется с помощью командлета [New – CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) .</span><span class="sxs-lookup"><span data-stu-id="db04a-147">File size limits are determined by the **MaxPhotoSizeKB** attribute in the client policy, defined with the [New-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) cmdlet.</span></span> <span data-ttu-id="db04a-148">По умолчанию предельный размер составляет 30 КБ.</span><span class="sxs-lookup"><span data-stu-id="db04a-148">The default size limit is 30 KB.</span></span> <span data-ttu-id="db04a-149">Максимальное значение 100 КБ.</span><span class="sxs-lookup"><span data-stu-id="db04a-149">The maximum value is 100 KB.</span></span> <span data-ttu-id="db04a-150">Разрешение изображения не ограничено, но при попытке использовать файл изображения, размер которого превышает предельный размер, он не будет загружен в клиенты Lync.</span><span class="sxs-lookup"><span data-stu-id="db04a-150">There is no restriction on the resolution of the image, but if you try to use an image file that exceeds the size limit it will not be downloaded to Lync clients.</span></span> <span data-ttu-id="db04a-151">Можно установить значение 0, чтобы отключить использование всех фотографий пользователей в Lync.</span><span class="sxs-lookup"><span data-stu-id="db04a-151">You can set the value to 0 to disable all user photos from being used in Lync.</span></span>

  - <span data-ttu-id="db04a-152">Внешние Федеративные контакты могут просматривать фотографии пользователей с веб-адреса.</span><span class="sxs-lookup"><span data-stu-id="db04a-152">User photos from a web address can be seen by external federated contacts.</span></span>

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a><span data-ttu-id="db04a-153">Управление фото пользователя с помощью командлетов Client Policy</span><span class="sxs-lookup"><span data-stu-id="db04a-153">Managing user’s photo with Client Policy cmdlets</span></span>

<span data-ttu-id="db04a-154">В Lync Server 2010 параметры политики клиента настраиваются с помощью командлетов CsClientPolicy.</span><span class="sxs-lookup"><span data-stu-id="db04a-154">In Lync Server 2010, client policy settings are configured with the CsClientPolicy cmdlets.</span></span> <span data-ttu-id="db04a-155">Настроенные параметры политики отправляются клиентам через наполнение данными по каналу.</span><span class="sxs-lookup"><span data-stu-id="db04a-155">The configured policy settings are sent to clients through in-band provisioning.</span></span> <span data-ttu-id="db04a-156">Два параметра командлетов CsClientPolicy, определяющие пользовательский интерфейс фотографии, — **дисплайфото** и **максфотосизекб**.</span><span class="sxs-lookup"><span data-stu-id="db04a-156">The two parameters of the CsClientPolicy cmdlets that determine the user photo experience are **DisplayPhoto** and **MaxPhotoSizeKB**.</span></span> <span data-ttu-id="db04a-157">Соответствующий параметр подготовки по основному **дисплайфото** и **максфотосизекб** называется "с **использованием**".</span><span class="sxs-lookup"><span data-stu-id="db04a-157">The corresponding in-band provisioning parameter for **DisplayPhoto** and **MaxPhotoSizeKB** is named **PhotoUsage**.</span></span> <span data-ttu-id="db04a-158">Значения параметра " **Фотоиспользование** " отправляются клиентам через **ендпоинтконфигуратион** **провисионграуп**.</span><span class="sxs-lookup"><span data-stu-id="db04a-158">Values for the **PhotoUsage** parameter are send to clients through the **endpointConfiguration** **provisionGroup**.</span></span> <span data-ttu-id="db04a-159">Более подробную информацию можно узнать [в статье Обзор политик и параметров клиента](https://go.microsoft.com/fwlink/?linkid=507470) .</span><span class="sxs-lookup"><span data-stu-id="db04a-159">See [Overview of Client Policies and Settings](https://go.microsoft.com/fwlink/?linkid=507470) for more information.</span></span>

<span data-ttu-id="db04a-160">Значение параметра **дисплайфото** определяет источник изображения фотографии пользователя.</span><span class="sxs-lookup"><span data-stu-id="db04a-160">The **DisplayPhoto** parameter value determines the source of the user's photo image.</span></span> <span data-ttu-id="db04a-161">Поддерживаемые значения приведены в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="db04a-161">The supported values are included in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db04a-162">Значение параметра Дисплайфото</span><span class="sxs-lookup"><span data-stu-id="db04a-162">DisplayPhoto parameter value</span></span></th>
<th><span data-ttu-id="db04a-163">Источник изображения</span><span class="sxs-lookup"><span data-stu-id="db04a-163">Image source</span></span></th>
<th><span data-ttu-id="db04a-164">Параметры клиента Lync 2010</span><span class="sxs-lookup"><span data-stu-id="db04a-164">Lync 2010 client settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db04a-165">Фотография</span><span class="sxs-lookup"><span data-stu-id="db04a-165">NoPhoto</span></span></p></td>
<td><p><span data-ttu-id="db04a-166">Нет</span><span class="sxs-lookup"><span data-stu-id="db04a-166">none</span></span></p></td>
<td><p><span data-ttu-id="db04a-167"><strong>Не показывать фотографию</strong></span><span class="sxs-lookup"><span data-stu-id="db04a-167"><strong>Do not show my picture</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db04a-168">фотофромадонли</span><span class="sxs-lookup"><span data-stu-id="db04a-168">PhotoFromADOnly</span></span></p></td>
<td><p><span data-ttu-id="db04a-169">Active Directory</span><span class="sxs-lookup"><span data-stu-id="db04a-169">Active Directory</span></span></p></td>
<td><p><span data-ttu-id="db04a-170"><strong>Корпоративный рисунок по умолчанию</strong></span><span class="sxs-lookup"><span data-stu-id="db04a-170"><strong>Default corporate picture</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db04a-171">AllPhotos</span><span class="sxs-lookup"><span data-stu-id="db04a-171">AllPhotos</span></span></p></td>
<td><p><span data-ttu-id="db04a-172">Веб-адрес</span><span class="sxs-lookup"><span data-stu-id="db04a-172">Web address</span></span></p></td>
<td><p><span data-ttu-id="db04a-173"><strong>Отображение изображения с веб-адреса</strong></span><span class="sxs-lookup"><span data-stu-id="db04a-173"><strong>Show a picture from a web address</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a><span data-ttu-id="db04a-174">Как клиент Lync 2010 получает фотографии</span><span class="sxs-lookup"><span data-stu-id="db04a-174">How Lync 2010 client gets photos</span></span>

<span data-ttu-id="db04a-175">В Lync 2010 Управление фотографиями пользователей осуществляется на сервере службой адресной книги.</span><span class="sxs-lookup"><span data-stu-id="db04a-175">In Lync 2010, user photos are managed on the server by the Address Book Service.</span></span> <span data-ttu-id="db04a-176">Клиент Lync получает фотографии пользователей, сначала запрашивая службу веб-запросов к адресной книге (ABWQ) на сервере, которая предоставляется через веб-службу расширения списка рассылки.</span><span class="sxs-lookup"><span data-stu-id="db04a-176">Lync client gets user photos by first querying the Address Book Web Query (ABWQ) service on the server, which is exposed through the Distribution List Expansion web service.</span></span> <span data-ttu-id="db04a-177">Клиент получает файл изображения и копирует его в кэш пользователя, чтобы не загружать изображение каждый раз, когда необходимо его отобразить.</span><span class="sxs-lookup"><span data-stu-id="db04a-177">The client receives the image file and then copies it to the user's cache to avoid downloading the image each time it needs to be displayed.</span></span> <span data-ttu-id="db04a-178">Значения атрибутов, возвращаемые из запроса, также хранятся в записи службы кэшированных адресных книг для пользователя.</span><span class="sxs-lookup"><span data-stu-id="db04a-178">The attribute values returned from the query are also stored in the cached Address Book Service entry for the user.</span></span> <span data-ttu-id="db04a-179">Служба адресной книги удаляет все кэшированные изображения каждые 24 часа, что означает, что для обновления новых образов пользователей в кэше на сервере может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="db04a-179">The Address Book Service deletes all cached images every 24 hours, which means that it can take up to 24 hours for new user images to be updated in the cache on the server.</span></span> <span data-ttu-id="db04a-180">Вы можете принудительно обновить кэш, используя командлет [Update – CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) .</span><span class="sxs-lookup"><span data-stu-id="db04a-180">You can force an update to the cache by using the [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet.</span></span>

<span data-ttu-id="db04a-181">Фотографии пользователей, включенные в состояние присутствия, также имеют связанное хэш-значение, которое Lync Client использует, чтобы определить, доступно ли более новое изображение.</span><span class="sxs-lookup"><span data-stu-id="db04a-181">User photos included in Presence status also have an associated hash value that Lync client uses to determine whether there is a newer image available.</span></span> <span data-ttu-id="db04a-182">Клиент автоматически уведомляет об изменениях файла изображения, используемого в состоянии присутствия.</span><span class="sxs-lookup"><span data-stu-id="db04a-182">The client is automatically notified of changes to the image file used in Presence status.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="db04a-183">Так как фотографии не хранятся в базе данных Галконтактс. DB, Загрузка фотографий пользователя не зависит от параметра <STRONG>аддрессбукаваилабилити</STRONG> в клиентской политике (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).</span><span class="sxs-lookup"><span data-stu-id="db04a-183">Because photos are not stored in the GalContacts.db database, downloading user photos is not dependent on the <STRONG>AddressBookAvailability</STRONG> setting in the client policy (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).</span></span>



</div>

<span data-ttu-id="db04a-184">Запрос к службе ABWQ включает следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="db04a-184">The query to the ABWQ service includes the following attributes:</span></span>

  - <span data-ttu-id="db04a-185">**Фотохэширование**     Хэш-значение двоичных данных фото и используется для определения того, изменилась ли текущая фотография.</span><span class="sxs-lookup"><span data-stu-id="db04a-185">**PhotoHash**   The hash value of the binary photo data, and is used to determine whether the current photo has changed.</span></span>

  - <span data-ttu-id="db04a-186">**Фоторелпас**     Относительный путь к файлу образа, хранящемуся на сервере.</span><span class="sxs-lookup"><span data-stu-id="db04a-186">**PhotoRelPath**   The relative path to the image file stored on the server.</span></span>

  - <span data-ttu-id="db04a-187">**Фоторазмер**     Размер файла изображения в байтах.</span><span class="sxs-lookup"><span data-stu-id="db04a-187">**PhotoSize**   The size of the image file, in bytes.</span></span>

  - <span data-ttu-id="db04a-188">**Временная метка**     Дата и время последней загрузки файла изображения с сервера и его копирование в кэш клиента.</span><span class="sxs-lookup"><span data-stu-id="db04a-188">**TimeStamp**   The date and time at which the image file was last downloaded from the server and copied to the client cache.</span></span>

<span data-ttu-id="db04a-189">Затем, после получения файла изображения, клиент Lync 2010 сравнивает значения атрибутов, возвращенные из запроса, со значениями атрибутов, полученными клиентом из встроенной подготовки, чтобы проверить, отличаются ли они.</span><span class="sxs-lookup"><span data-stu-id="db04a-189">Next, after retrieving the image file, Lync 2010 client compares the attribute values returned from the query against the attribute values received by the client from in-band provisioning to see if they are different.</span></span> <span data-ttu-id="db04a-190">Если значения отличаются, клиент получает файл изображения, выполнившего вход пользователя, с помощью HTTP-запроса GET.</span><span class="sxs-lookup"><span data-stu-id="db04a-190">If the values are different, the client retrieves the image file of the signed-in user with an HTTP GET request.</span></span>

<span data-ttu-id="db04a-191">Кроме того, клиент сверяет с сервером каждые 24 часа с момента создания кэшированной версии файла образа для сравнения значения атрибута " **Фотохеширование** " на сервере со значением на клиенте.</span><span class="sxs-lookup"><span data-stu-id="db04a-191">Additionally, the client checks with the server every 24 hours from the time at which the cached version of the image file was created to compare the value of the **PhotoHash** attribute on the server with the value on the client.</span></span> <span data-ttu-id="db04a-192">Если значения отличаются, клиент знает, что файл изображения изменился.</span><span class="sxs-lookup"><span data-stu-id="db04a-192">If the values are different, the client knows that the image file has changed.</span></span> <span data-ttu-id="db04a-193">Чтобы получить обновленный файл изображения, клиент снова запрашивает службу ABWQ, чтобы обновить файл изображения в клиентском кэше с помощью файла изображения на сервере, который также сбрасывает **метку времени** для файла в кэше клиента.</span><span class="sxs-lookup"><span data-stu-id="db04a-193">To obtain the updated image file, the client again queries the ABWQ service to update the image file in the client cache with the image file on the server, which also resets the **TimeStamp** on the file in the client cache.</span></span>

<span data-ttu-id="db04a-194">Ниже приведен пример ответа на запрос для службы ABWQ:</span><span class="sxs-lookup"><span data-stu-id="db04a-194">The following is an example response to a query to the ABWQ service:</span></span>
```xml
    <Attribute>
              <Name>PhotoRelPath</Name>
              <Value>efa6096aed2746cb9ab2037f7dbdde9d.f2eeeb5946db54a7aa607ecd3ae09d
              95.photo</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
              <Name>PhotoHash</Name>
              <Value>f2eeeb5946db54a7aa607ecd3ae09d95</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
         <Name>PhotoSize</Name>
         <Value>4620</Value>
         <Valuesxmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
    i:nil="true" />
    </Attribute>
```

</div>

</div>

<div>

## <a name="user-photos-in-lync-2013"></a><span data-ttu-id="db04a-195">Фотографии пользователей в Lync 2013</span><span class="sxs-lookup"><span data-stu-id="db04a-195">User photos in Lync 2013</span></span>

<span data-ttu-id="db04a-196">Lync 2013 представил поддержку изображений с высоким разрешением для фотографий пользователей.</span><span class="sxs-lookup"><span data-stu-id="db04a-196">Lync 2013 introduced support for high-resolution images for user photos.</span></span> <span data-ttu-id="db04a-197">Lync 2013 также включает поддержку хранения фотографий пользователей в почтовом ящике пользователя на сервере Exchange 2013, что приводит к удалению разрешения и размера изображения в Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="db04a-197">Lync 2013 also includes support for storing user photos in the user's mailbox on Exchange 2013, which removes the image resolution and size limitations present in Lync 2010.</span></span> <span data-ttu-id="db04a-198">Фотографии пользователей в Lync 2013 могут быть не более 648 пикселей на 648 пикселов размером до 20 МБ.</span><span class="sxs-lookup"><span data-stu-id="db04a-198">User photos in Lync 2013 can be up to 648 pixels by 648 pixels with a file size of up to 20 MB.</span></span> <span data-ttu-id="db04a-199">Фотографии высокого разрешения в Lync 2013 должны находиться в почтовом ящике пользователя на сервере Exchange 2013, и поддерживаются только в клиенте Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="db04a-199">High-resolution photos in Lync 2013 must be located in the user's mailbox on Exchange 2013, and are supported only with Lync 2013 client.</span></span> <span data-ttu-id="db04a-200">Эта интеграция с Exchange использует преимущества новой платформы проверки подлинности, входящей в версии 2013 Lync, Exchange и SharePoint, называемые OAuth.</span><span class="sxs-lookup"><span data-stu-id="db04a-200">This integration with Exchange takes advantage of the new authorization framework included in the 2013 versions of Lync, Exchange, and SharePoint called Oauth.</span></span>

<span data-ttu-id="db04a-201">Если в вашем развертывании не используется Exchange 2013, поддержка фотографий пользователей выполняется так же, как и в Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="db04a-201">If Exchange 2013 is not used in your deployment, support for user photos is the same as with Lync 2010.</span></span> <span data-ttu-id="db04a-202">Тем не менее, пользовательские параметры для выбора фотографии отличаются в клиенте Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="db04a-202">However, the user options to choose the photo to use are different in Lync 2013 client.</span></span> <span data-ttu-id="db04a-203">В клиенте Lync 2013 пользователи могут выбрать **Скрыть мое изображение** или **Показать фотографию**.</span><span class="sxs-lookup"><span data-stu-id="db04a-203">In Lync 2013 client, users can select either **Hide my picture** or **Show my picture**.</span></span> <span data-ttu-id="db04a-204">Параметр **Показывать изображение с веб-сайта** по умолчанию недоступен, но его можно включить, назначая политику клиента.</span><span class="sxs-lookup"><span data-stu-id="db04a-204">The option **Show a picture from a website** is not available by default, but can be enabled by assigning a client policy.</span></span>

<div>

## <a name="hide-my-picture"></a><span data-ttu-id="db04a-205">Скрыть фотографию</span><span class="sxs-lookup"><span data-stu-id="db04a-205">Hide my picture</span></span>

<span data-ttu-id="db04a-206">Параметры фотографий пользователей находятся в диалоговом окне " **Параметры** " в Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="db04a-206">Settings for user photos are on the **Options** dialog in Lync 2013.</span></span> <span data-ttu-id="db04a-207">При выборе параметра **скрыть мою**фотографию Фото пользователя не отображается в клиенте Lync, но фотография по-прежнему отображается в карточке контакта и вне Lync.</span><span class="sxs-lookup"><span data-stu-id="db04a-207">When you choose **Hide my picture**, no user photo is displayed for you in Lync client, but your photo is still displayed on your contact card and outside of Lync.</span></span>

</div>

<div>

## <a name="show-my-picture"></a><span data-ttu-id="db04a-208">Показать фотографию</span><span class="sxs-lookup"><span data-stu-id="db04a-208">Show my picture</span></span>

<span data-ttu-id="db04a-209">При выборе параметра **Показать мой рисунок** фотография пользователя отображается в клиенте Lync и других пользователях в беседах Lync.</span><span class="sxs-lookup"><span data-stu-id="db04a-209">When you choose the **Show my picture** option, your user photo is displayed in your Lync client and to other users in Lync conversations.</span></span> <span data-ttu-id="db04a-210">Используемое изображение хранится в доменных СЛУЖБах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="db04a-210">The image used is the one stored in AD DS.</span></span>

</div>

<div>

## <a name="show-a-picture-from-a-website"></a><span data-ttu-id="db04a-211">Отображение изображения с веб-сайта</span><span class="sxs-lookup"><span data-stu-id="db04a-211">Show a picture from a website</span></span>

<span data-ttu-id="db04a-212">Параметр **Показывать рисунок из веб-сайта** становится доступным в Lync 2013 после того, как политика клиента настроена на включение.</span><span class="sxs-lookup"><span data-stu-id="db04a-212">The **Show picture from a website** option becomes available in Lync 2013 after a client policy is set to enable it.</span></span> <span data-ttu-id="db04a-213">Версия клиента должна быть более новой, чем 15.0.4535.1002, которая устанавливается вместе с [накопительными обновлениями Lync: ноябрь 2013](https://go.microsoft.com/fwlink/p/?linkid=509908).</span><span class="sxs-lookup"><span data-stu-id="db04a-213">The client version must be newer than 15.0.4535.1002, which is installed with the [Lync Cumulative Updates: November 2013](https://go.microsoft.com/fwlink/p/?linkid=509908).</span></span> <span data-ttu-id="db04a-214">Пользователям может потребоваться выйти из, а затем снова войти в систему, чтобы просмотреть изменения в клиенте.</span><span class="sxs-lookup"><span data-stu-id="db04a-214">Users may need to log out and then back in again to see the changes in the client.</span></span>

<span data-ttu-id="db04a-215">Вы можете настроить клиентскую политику, чтобы включить **Отображение изображения с веб-сайта** , запустив политику [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) в командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="db04a-215">You can set the client policy to enable to **Show picture from a website** setting by running the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) policy in the Lync Server Management Shell.</span></span> <span data-ttu-id="db04a-216">В приведенном ниже примере командлетов показано, как настроить политику глобально для всех пользователей в развертывании:</span><span class="sxs-lookup"><span data-stu-id="db04a-216">The following example cmdlets demonstrate how to set the policy globally for all users in your deployment:</span></span>

   ```powershell
    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
   ```

   ```powershell
    $po=Get-CsClientPolicy -Identity Global
   ```

   ```powershell
    $po.PolicyEntry.Add($pe)
   ```

   ```powershell
    Set-CsClientPolicy -Instance $po
   ```


<span data-ttu-id="db04a-217">Когда изображение передается в почтовый ящик пользователя, Exchange автоматически создает версию изображения с более низким разрешением, которую можно использовать в клиентских приложениях.</span><span class="sxs-lookup"><span data-stu-id="db04a-217">When an image is uploaded to the user’s mailbox, Exchange automatically creates a lower resolution version of the image which can be used in client applications.</span></span> <span data-ttu-id="db04a-218">Фотография пользователя также обновлена в доменных СЛУЖБах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="db04a-218">The user photo is also updated in AD DS.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="db04a-219">При обновлении файла изображения в доменных СЛУЖБах Active Directory создается и используется изображение пикселя 48 x 48 в thumbnailPhoto в AD DS.</span><span class="sxs-lookup"><span data-stu-id="db04a-219">When an image file is updated in AD DS, a 48 x 48 pixel image is created and used for the thumbnailPhoto in AD DS.</span></span> <span data-ttu-id="db04a-220">Все существующие изображения заменяются.</span><span class="sxs-lookup"><span data-stu-id="db04a-220">Any existing image is replaced.</span></span> <span data-ttu-id="db04a-221">Таким образом, если вы добавили изображение 96 x 96 в AD DS, оно будет перезаписано на новое изображение 48 x 48.</span><span class="sxs-lookup"><span data-stu-id="db04a-221">So if you added a 96 x 96 image to AD DS, it will be overwritten with the new 48 x 48 image.</span></span> <span data-ttu-id="db04a-222">Это важно только для пользователей в вашей среде с помощью клиентов Lync 2010, так как эти клиенты будут получать фотографии пользователей из доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="db04a-222">This is only important is you have users in your environment using Lync 2010 clients, as those clients will obtain user photos from AD DS.</span></span> <span data-ttu-id="db04a-223">Вы можете импортировать изображения 96 x 96 пикселей, чтобы заменить созданные AD DS, если в Организации есть клиенты Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="db04a-223">You can import 96 x 96 pixel images to replace the ones created by AD DS if you have Lync 2010 clients in your organization.</span></span>



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a><span data-ttu-id="db04a-224">Поддержка Фото пользователей в Lync 2013</span><span class="sxs-lookup"><span data-stu-id="db04a-224">User photo support in Lync 2013</span></span>

<span data-ttu-id="db04a-225">В Lync 2013 для фотографий пользователей поддерживаются три разрешения изображений, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="db04a-225">In Lync 2013, three image resolutions are supported for user photos as described in the following table.</span></span> <span data-ttu-id="db04a-226">Используемое изображение определяется параметром политики клиента, назначенным пользователям Lync.</span><span class="sxs-lookup"><span data-stu-id="db04a-226">The image that is used is determined by the client policy setting assigned to Lync users.</span></span> <span data-ttu-id="db04a-227">Для получения дополнительных сведений обратитесь к разделу "Управление фото пользователя с помощью командлетов Client Policy" этой статьи.</span><span class="sxs-lookup"><span data-stu-id="db04a-227">See “Managing user’s photo with Client Policy cmdlets” in this topic for more information.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db04a-228">Разрешение изображения (ПКС)</span><span class="sxs-lookup"><span data-stu-id="db04a-228">Image resolution (pixels)</span></span></th>
<th><span data-ttu-id="db04a-229">Для приложений</span><span class="sxs-lookup"><span data-stu-id="db04a-229">Application</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db04a-230">48 x 48</span><span class="sxs-lookup"><span data-stu-id="db04a-230">48 x 48</span></span></p></td>
<td><p><span data-ttu-id="db04a-231">Используется, если изображение с более высоким разрешением не выбрано</span><span class="sxs-lookup"><span data-stu-id="db04a-231">Used if no higher resolution image is selected</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db04a-232">96 x 96</span><span class="sxs-lookup"><span data-stu-id="db04a-232">96 x 96</span></span></p></td>
<td><p><span data-ttu-id="db04a-233">Используется в Outlook Web App и Outlook 2013</span><span class="sxs-lookup"><span data-stu-id="db04a-233">Used in Outlook Web App and Outlook 2013</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db04a-234">648 x 648</span><span class="sxs-lookup"><span data-stu-id="db04a-234">648 x 648</span></span></p></td>
<td><p><span data-ttu-id="db04a-235">Используется в Lync 2013 для настольных компьютеров и Lync 2013 Web App</span><span class="sxs-lookup"><span data-stu-id="db04a-235">Used in Lync 2013 desktop client and Lync 2013 Web App</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="db04a-236">Любой пользователь с почтовым ящиком, включенным в Exchange 2013, может отправить другое изображение, включая фотографии высокого разрешения, с помощью Outlook Web Access или параметров клиента Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="db04a-236">Any user with a mailbox enabled in Exchange 2013 can upload a different image, including high-resolution photos, through Outlook Web Access or Lync 2013 client options.</span></span> <span data-ttu-id="db04a-237">Для используемых изображений рекомендуются следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="db04a-237">The recommended settings for images used include:</span></span>

  - <span data-ttu-id="db04a-238">**Разрешение изображения**     648 x 648 пикселей</span><span class="sxs-lookup"><span data-stu-id="db04a-238">**Image Resolution**   648 by 648 pixels</span></span>

  - <span data-ttu-id="db04a-239">**Глубина цвета**     24 бита</span><span class="sxs-lookup"><span data-stu-id="db04a-239">**Color Depth**   24-bit</span></span>

  - <span data-ttu-id="db04a-240">**Размер**     файла изображения до 20 МБ</span><span class="sxs-lookup"><span data-stu-id="db04a-240">**Image file size**   up to 20 MB</span></span>

  - <span data-ttu-id="db04a-241">**Формат файла**     РИСУНКИ</span><span class="sxs-lookup"><span data-stu-id="db04a-241">**File format**   JPEG</span></span>

<span data-ttu-id="db04a-242">Типичное 24-разрядное изображение JPEG, размер которого составляет 648 пикселей на 648 пикселей, имеет размер около 240 КБ, поэтому 1 МБ дискового пространства требуется для каждых 4 пользовательских фотографий.</span><span class="sxs-lookup"><span data-stu-id="db04a-242">A typical 24-bit JPEG image that is 648 pixels by 648 pixels has a file size of about 240 KB, so 1 MB of storage space is needed for every 4 user photos.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

