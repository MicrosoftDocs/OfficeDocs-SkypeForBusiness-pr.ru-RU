---
title: 'Lync Server 2013: Настройка использования фотографий высокого разрешения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the use of high-resolution photos in Lync Server 2013
ms:assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688150(v=OCS.15)
ms:contentKeyID: 49733753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a49618cd4039163f22d44f358c29a802037b8b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a><span data-ttu-id="1bb1e-102">Настройка использования фотографий высокого разрешения в Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1bb1e-102">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1bb1e-103">_**Последнее изменение темы:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="1bb1e-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="1bb1e-104">Microsoft Lync Server 2010 предоставил пользователям возможность просматривать фотографии их контактов (а также предоставлять доступ к своим фотографиям другим пользователям).</span><span class="sxs-lookup"><span data-stu-id="1bb1e-104">Microsoft Lync Server 2010 provided the ability for users to view photos of their contacts (and to make their own photos available to others).</span></span> <span data-ttu-id="1bb1e-105">Обычно эти фотографии хранятся в атрибуте пользователя thumbnailPhoto в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1bb1e-105">Typically these photos were stored as part of the user's thumbnailPhoto attribute in Active Directory.</span></span> <span data-ttu-id="1bb1e-106">Это накладывает серьезные ограничения на размер и разрешение фотографий: атрибут thumbnailPhoto может содержать фотографии с максимальным разрешением 48 x 48 пикселей.</span><span class="sxs-lookup"><span data-stu-id="1bb1e-106">That placed a serious limitation on the size and resolution of the photos: the thumbnailPhoto attribute can only hold a photograph with a maximum size of 48 pixels by 48 pixels.</span></span>

<span data-ttu-id="1bb1e-107">Однако в Microsoft Lync Server 2013 фотографии могут храниться в почтовом ящике пользователя Microsoft Exchange Server 2013; Это позволяет создавать фотографии размером до 648 пикселей на 648 пикселей.</span><span class="sxs-lookup"><span data-stu-id="1bb1e-107">In Microsoft Lync Server 2013, however, photos can be stored in a user's Microsoft Exchange Server 2013 mailbox; that allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="1bb1e-108">Кроме того, Exchange 2013 может автоматически изменять размер этих фотографий для использования в различных продуктах.</span><span class="sxs-lookup"><span data-stu-id="1bb1e-108">In addition to that, Exchange 2013 can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="1bb1e-109">Как правило, используются фотографии трех размеров и разрешений, которые перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="1bb1e-109">Typically that means three different photo sizes and resolutions:</span></span>

  - <span data-ttu-id="1bb1e-110">Размер 48 x 48 пикселей используется для атрибута thumbnailPhoto в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1bb1e-110">48 pixels by 48 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="1bb1e-111">Если вы отправите фотографию в Exchange 2013, Exchange автоматически создаст ее версию 48 на 48 пикселей и обновите атрибут thumbnailPhoto пользователя.</span><span class="sxs-lookup"><span data-stu-id="1bb1e-111">If you upload a photo to Exchange 2013 Exchange will automatically create a 48 pixel by 48 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="1bb1e-112">Однако обратите внимание, что обратное неверно: при обновлении атрибута thumbnailPhoto в Active Directory фотография в почтовом ящике пользователя Exchange 2013 не будет автоматически обновляться.</span><span class="sxs-lookup"><span data-stu-id="1bb1e-112">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange 2013 mailbox will not automatically be updated.</span></span>

  - <span data-ttu-id="1bb1e-113">96 x 96 пикселей для использования в Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App и Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="1bb1e-113">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App, and Lync 2013.</span></span>

  - <span data-ttu-id="1bb1e-114">648 x 648 пикселей для использования в Lync 2013 и Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="1bb1e-114">648 pixels by 648 pixels for use in Lync 2013 and Microsoft Lync Web App.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1bb1e-p104">При наличии достаточных ресурсов рекомендуется отправлять фотографии с размером 648 x 648 пикселей; это обеспечит максимальное разрешение и оптимальное качество изображения в любых приложениях Office 2013. Размер JPEG-файла фотографии с разрешением 648 x 648 и глубиной 24 бита составляет приблизительно 240 килобайт. Это значит, что для каждых 4 пользовательских фотографий потребуется примерно 1 мегабайт дискового пространства.</span><span class="sxs-lookup"><span data-stu-id="1bb1e-p104">If you have the resources, it is recommended that you upload 648x648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications. Each JPEG photo with a size of 648x648 and a depth of 24 bits results in a file size of approximately 240 kilobytes. That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span>



</div>

<span data-ttu-id="1bb1e-118">Фотографии высокого разрешения, доступ к которым осуществляется с помощью веб-служб Exchange, могут отправлять пользователи, на которых работает Outlook 2013 Web App; пользователям разрешено обновлять только свои фотографии.</span><span class="sxs-lookup"><span data-stu-id="1bb1e-118">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="1bb1e-119">Однако администраторы могут обновить фотографию для любого пользователя с помощью командной консоли Exchange и серии команд Windows PowerShell, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="1bb1e-119">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="1bb1e-120">В первой команде в предыдущем примере используется командлет Get-Content для считывания содержимого файла C:\\Photos\\kenmyer. jpg и сохранения этих данных в переменной с именем $Photo.</span><span class="sxs-lookup"><span data-stu-id="1bb1e-120">The first command in the preceding example uses the Get-Content cmdlet to read the contents of the file C:\\Photos\\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="1bb1e-121">Во второй команде командлет Exchange Set-UserPhoto используется для отправки фотографии и вложения этой фотографии в учетную запись пользователя Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="1bb1e-121">In the second command, the Exchange cmdlet Set-UserPhoto is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1bb1e-122">В данном примере в качестве идентификатора учетной записи используется отображаемое имя пользователя Ken Myer в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1bb1e-122">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="1bb1e-123">Для ссылки на учетную запись пользователя можно использовать и другие идентификаторы, например, SMTP-адрес пользователя или имя участника-пользователя.</span><span class="sxs-lookup"><span data-stu-id="1bb1e-123">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="1bb1e-124"><A href="https://go.microsoft.com/fwlink/p/?linkid=268536">https://go.microsoft.com/fwlink/p/?LinkId=268536</A> Для получения дополнительных сведений обратитесь к документации по командлету Set – UserPhoto.</span><span class="sxs-lookup"><span data-stu-id="1bb1e-124">See the documentation for the Set-UserPhoto cmdlet at <A href="https://go.microsoft.com/fwlink/p/?linkid=268536">https://go.microsoft.com/fwlink/p/?LinkId=268536</A> for more information</span></span>



</div>

<span data-ttu-id="1bb1e-p108">Отправка фотографии не означает, что она будет автоматически назначена учетной записи пользователя Ken Myer. После отправки фотография просто будет отображаться в режиме предварительного просмотра на странице параметров Outlook Web App. Чтобы назначить фотографию учетной записи, пользователь должен нажать кнопку **Сохранить** на странице параметров или же администратор должен выполнить третью команду данного примера. В третьей команде используется параметр Save для назначения фотографии учетной записи пользователя Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="1bb1e-p108">Uploading the photo does not equate to assigning that photo to Ken Myer's user account. Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page. To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example. That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="1bb1e-129">Чтобы убедиться, что новая фотография назначена учетной записи пользователя, Ken Myer может войти в Lync 2013, выбрать **Параметры**, а затем выбрать **мою фотографию**.</span><span class="sxs-lookup"><span data-stu-id="1bb1e-129">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Lync 2013, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="1bb1e-130">В качестве личного фото пользователя Ken Myer должна отобразиться новая фотография.</span><span class="sxs-lookup"><span data-stu-id="1bb1e-130">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="1bb1e-131">Администратор может проверить фотографию любого пользователя, введя в адресной строке Internet Explorer URL-адрес, подобный показанному ниже.</span><span class="sxs-lookup"><span data-stu-id="1bb1e-131">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

<span data-ttu-id="1bb1e-132">Если администратор может просматривать фотографию с помощью Internet Explorer, но пользователь не может просматривать его фотографию в Lync 2013, то, как правило, указывает на проблему с подключением к веб-службам Exchange или службе автообнаружения Exchange.</span><span class="sxs-lookup"><span data-stu-id="1bb1e-132">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Lync 2013, that typically indicates a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>

<span data-ttu-id="1bb1e-133">Обратите внимание, что дополнительные настройки не требуются для того, чтобы сделать эту фотографию доступной в Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="1bb1e-133">Note, too that no additional configuration is required in order to make this photo available in Lync 2013.</span></span> <span data-ttu-id="1bb1e-134">Вместо этого фотография будет мгновенно доступна после отправки и запуска командлета Set – UserPhoto.</span><span class="sxs-lookup"><span data-stu-id="1bb1e-134">Instead, the photo will be instantly available after it has been uploaded and the Set-UserPhoto cmdlet has been run.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

