---
title: Настройка использования фотографий высокого разрешения в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 'Сводка: Настройка использования фотографий высокого разрешения в Exchange Server 2016 или Exchange Server 2013 и Skype для бизнеса Server.'
ms.openlocfilehash: d52cdb2d84fedba0dcbec97cbca4074b1ae12a84
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278208"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a><span data-ttu-id="c77c1-103">Настройка использования фотографий высокого разрешения в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c77c1-103">Configure the use of high-resolution photos in Skype for Business Server</span></span>
 
<span data-ttu-id="c77c1-104">**Сводка:** Настройте использование фотографий высокого разрешения в Exchange Server 2016 или Exchange Server 2013 и Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="c77c1-104">**Summary:** Configure the use of high-resolution photos in Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="c77c1-105">В Skype для бизнеса Server фотографии могут храниться в почтовом ящике Exchange Server 2016 или Exchange Server 2013, что позволяет создавать фотографии размером до 648 пикселей на 648 пикселей.</span><span class="sxs-lookup"><span data-stu-id="c77c1-105">In Skype for Business Server photos can be stored in a user's Exchange Server 2016 or Exchange Server 2013 mailbox, which allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="c77c1-106">Кроме того, Exchange Server может автоматически менять размер этих фотографий, чтобы использовать их в разных продуктах при необходимости.</span><span class="sxs-lookup"><span data-stu-id="c77c1-106">In addition, Exchange Server can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="c77c1-107">Как правило, используются фотографии трех размеров и разрешений, которые перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="c77c1-107">Typically that means three different photo sizes and resolutions:</span></span>
  
- <span data-ttu-id="c77c1-108">Размер 64 x 64 пикселя используется для атрибута thumbnailPhoto в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c77c1-108">64 pixels by 64 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="c77c1-109">Если вы отправите фотографию на сервер Exchange Server, Exchange автоматически создаст 64 пикселей на версии 64 пикселей этой фотографии и обновите атрибут Фотоэскиз пользователя.</span><span class="sxs-lookup"><span data-stu-id="c77c1-109">If you upload a photo to Exchange Server, Exchange will automatically create a 64 pixel by 64 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="c77c1-110">Однако обратите внимание на то, что обратное неверно: Если вы вручную обновите атрибут Фотоэскиз в Active Directory, то фотография в почтовом ящике Exchange пользователя не будет обновляться автоматически.</span><span class="sxs-lookup"><span data-stu-id="c77c1-110">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange mailbox will not automatically be updated.</span></span>
    
- <span data-ttu-id="c77c1-111">96 пикселей на 96 пикселей для работы в веб-приложении Microsoft Outlook 2013, Microsoft Outlook 2013, Skype для бизнеса Web App и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c77c1-111">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App, and Skype for Business.</span></span>
    
- <span data-ttu-id="c77c1-112">648 пикселей на 648 пикселей для использования в Skype для бизнеса и Skype для бизнеса Web App Skype для бизнеса Web App.</span><span class="sxs-lookup"><span data-stu-id="c77c1-112">648 pixels by 648 pixels for use in Skype for Business and Skype for Business Web App Skype for Business Web App.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c77c1-113">Если у вас есть ресурсы, рекомендуется загрузить фотографии 648 x 648; обеспечивает максимальное разрешение и оптимальное качество изображения в любом из приложений Office 2013.</span><span class="sxs-lookup"><span data-stu-id="c77c1-113">If you have the resources, it is recommended that you upload 648 x 648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications.</span></span> <span data-ttu-id="c77c1-114">Каждая фотография JPEG с размером 648 x 648 и глубиной 24 бита составляет примерно 240 КБайт.</span><span class="sxs-lookup"><span data-stu-id="c77c1-114">Each JPEG photo with a size of 648 x 648 and a depth of 24 bits results in a file size of approximately 240 kilobytes.</span></span> <span data-ttu-id="c77c1-115">Это значит, что для каждых 4 пользовательских фотографий потребуется примерно 1 мегабайт дискового пространства.</span><span class="sxs-lookup"><span data-stu-id="c77c1-115">That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span> 
  
<span data-ttu-id="c77c1-116">Фотографии высокого разрешения, доступ к которым осуществляется с помощью веб-служб Exchange, могут отправлять пользователи, которые работают с Outlook 2013 Web App; Пользователи могут обновлять только свои фотографии.</span><span class="sxs-lookup"><span data-stu-id="c77c1-116">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="c77c1-117">Однако администраторы могут обновлять фотографию для любого пользователя с помощью командной консоли Exchange и последовательности команд Windows PowerShell, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="c77c1-117">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>
  
```
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="c77c1-118">Первая команда в предыдущем примере использует `Get-Content` командлет для чтения содержимого файла к:\фотос\кенмер.ЖПГ и хранения данных в переменной с именем $Photo.</span><span class="sxs-lookup"><span data-stu-id="c77c1-118">The first command in the preceding example uses the `Get-Content` cmdlet to read the contents of the file C:\Photos\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="c77c1-119">Во второй команде с помощью командлета `Set-UserPhoto` Exchange можно отправить фотографию и прикрепить ее к учетной записи пользователя Кен мер.</span><span class="sxs-lookup"><span data-stu-id="c77c1-119">In the second command, the Exchange cmdlet `Set-UserPhoto` is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c77c1-120">В данном примере в качестве идентификатора учетной записи используется отображаемое имя пользователя Ken Myer в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c77c1-120">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="c77c1-121">Для ссылки на учетную запись пользователя можно использовать и другие идентификаторы, например SMTP-адрес пользователя или имя участника-пользователя.</span><span class="sxs-lookup"><span data-stu-id="c77c1-121">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="c77c1-122">Дополнительные сведения о командлете Set-Усерфото см. [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) в документации</span><span class="sxs-lookup"><span data-stu-id="c77c1-122">See the documentation for the Set-UserPhoto cmdlet at [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) for more information</span></span>
  
<span data-ttu-id="c77c1-p107">Отправка фотографии не означает, что она будет автоматически назначена учетной записи пользователя Ken Myer. После отправки фотография просто будет отображаться в режиме предварительного просмотра на странице параметров Outlook Web App. Чтобы назначить фотографию учетной записи, пользователь должен нажать кнопку **Сохранить** на странице параметров или же администратор должен выполнить третью команду данного примера. В третьей команде используется параметр Save для назначения фотографии учетной записи пользователя Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="c77c1-p107">Uploading the photo does not equate to assigning that photo to Ken Myer's user account. Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page. To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example. That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="c77c1-127">Чтобы убедиться в том, что новая фотография назначена учетной записи пользователя, Кен мер может войти в Skype для бизнеса, выбрать **Параметры**, а затем выбрать **мою фотографию**.</span><span class="sxs-lookup"><span data-stu-id="c77c1-127">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Skype for Business, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="c77c1-128">В качестве личной фотографии пользователя Ken Myer должна отобразиться новая фотография.</span><span class="sxs-lookup"><span data-stu-id="c77c1-128">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="c77c1-129">Администратор может проверить фотографию любого пользователя, введя в адресной строке Internet Explorer URL-адрес, подобный показанному ниже.</span><span class="sxs-lookup"><span data-stu-id="c77c1-129">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&amp;size=HR648x648
```

<span data-ttu-id="c77c1-130">Если администратор может просмотреть фотографию с помощью Internet Explorer, но пользователь не может просмотреть ее фотографию в Skype для бизнеса, возможно, возникла проблема с подключением к веб-службам Exchange или службе автообнаружения Exchange.</span><span class="sxs-lookup"><span data-stu-id="c77c1-130">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Skype for Business there may be a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>
  
<span data-ttu-id="c77c1-131">Обратите внимание, что для того чтобы фотография была доступна в Skype для бизнеса, требуется дополнительная настройка.</span><span class="sxs-lookup"><span data-stu-id="c77c1-131">Note, too that no additional configuration is required in order to make this photo available in Skype for Business.</span></span> <span data-ttu-id="c77c1-132">Вместо этого фотография будет мгновенно доступна после отправки и запуска `Set-UserPhoto` командлета.</span><span class="sxs-lookup"><span data-stu-id="c77c1-132">Instead, the photo will be instantly available after it has been uploaded and the `Set-UserPhoto` cmdlet has been run.</span></span>
