---
title: Настройка использования фотографий с высоким разрешением в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: Сводка. Настройте использование фотографий с высоким разрешением в Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 г., или Exchange Online и Skype для бизнеса Server.
ms.openlocfilehash: f5cc44f9f390c1d3241e7fae68054754ff7b0f76
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109805"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a><span data-ttu-id="15d4c-103">Настройка использования фотографий с высоким разрешением в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="15d4c-103">Configure the use of high-resolution photos in Skype for Business Server</span></span>
 
<span data-ttu-id="15d4c-104">**Сводка:** Настройка использования фотографий с высоким разрешением в Exchange Server 2019, Exchange Server 2016 г. Exchange Server 2013 г. или Exchange Online и Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="15d4c-104">**Summary:** Configure the use of high-resolution photos in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013, or Exchange Online and Skype for Business Server.</span></span>
  
<span data-ttu-id="15d4c-105">В Skype для бизнеса Server фотографии можно хранить в Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 г., или почтовом ящике Exchange Online, который позволяет размер фотографий до 648 пикселей на 648 пикселей.</span><span class="sxs-lookup"><span data-stu-id="15d4c-105">In Skype for Business Server, photos can be stored in a user's Exchange Server 2019, Exchange Server 2016, Exchange Server 2013, or Exchange Online mailbox, which allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="15d4c-106">Кроме того, Exchange Server автоматически можно использовать эти фотографии для использования в различных продуктах по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="15d4c-106">In addition, Exchange Server can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="15d4c-107">Как правило, используются фотографии трех размеров и разрешений, которые перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="15d4c-107">Typically that means three different photo sizes and resolutions:</span></span>
  
- <span data-ttu-id="15d4c-108">64 пикселя на 64 пикселя , размер, используемый для атрибута Active Directory thumbnailPhoto.</span><span class="sxs-lookup"><span data-stu-id="15d4c-108">64 pixels by 64 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="15d4c-109">Если вы загрузите фотографию в Exchange Server, Exchange автоматически создаст 64 пикселя на 64 пикселя версии этой фотографии и обновит атрибут эскиза пользователяPhoto.</span><span class="sxs-lookup"><span data-stu-id="15d4c-109">If you upload a photo to Exchange Server, Exchange will automatically create a 64 pixel by 64 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="15d4c-110">Обратите внимание, однако, что обратное не верно: если вручную обновить атрибут thumbnailPhoto в Active Directory, фотография в почтовом ящике Exchange пользователя не будет автоматически обновляться.</span><span class="sxs-lookup"><span data-stu-id="15d4c-110">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange mailbox will not automatically be updated.</span></span>
    
- <span data-ttu-id="15d4c-111">96 пикселей на 96 пикселей для использования в Веб-приложении Microsoft Outlook 2013, Microsoft Outlook 2013, Skype для бизнеса и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="15d4c-111">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App, and Skype for Business.</span></span>
    
- <span data-ttu-id="15d4c-112">648 пикселей на 648 пикселей для использования в Skype для бизнеса и Skype для бизнеса Веб-приложение Skype для бизнеса Веб-приложение.</span><span class="sxs-lookup"><span data-stu-id="15d4c-112">648 pixels by 648 pixels for use in Skype for Business and Skype for Business Web App Skype for Business Web App.</span></span>
    
> [!NOTE]
> <span data-ttu-id="15d4c-113">Если у вас есть ресурсы, рекомендуется загрузить 648 x 648 фотографий; обеспечивает максимальное разрешение и оптимальное качество изображения в любом из приложений Office 2013.</span><span class="sxs-lookup"><span data-stu-id="15d4c-113">If you have the resources, it is recommended that you upload 648 x 648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications.</span></span> <span data-ttu-id="15d4c-114">Каждая фотография JPEG размером 648 x 648 и глубиной 24 бита приводит к размеру файла примерно 240 килобайт.</span><span class="sxs-lookup"><span data-stu-id="15d4c-114">Each JPEG photo with a size of 648 x 648 and a depth of 24 bits results in a file size of approximately 240 kilobytes.</span></span> <span data-ttu-id="15d4c-115">Это значит, что для каждых 4 пользовательских фотографий потребуется примерно 1 мегабайт дискового пространства.</span><span class="sxs-lookup"><span data-stu-id="15d4c-115">That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span> 
  
<span data-ttu-id="15d4c-116">Фотографии с высоким разрешением, к которым можно получить доступ с помощью веб-служб Exchange, могут быть загружены пользователями, которые запускают Веб-приложение Outlook 2013; пользователям разрешено обновлять только собственные фотографии.</span><span class="sxs-lookup"><span data-stu-id="15d4c-116">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="15d4c-117">Администраторы, однако, могут обновлять фотографию для любого пользователя с помощью командной оболочки Exchange и Windows PowerShell команд, аналогичных следующим:</span><span class="sxs-lookup"><span data-stu-id="15d4c-117">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>
  
```powershell
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="15d4c-118">Первая команда в предыдущем примере использует командлет для чтения содержимого файла C:\Photos\Kenmyer.jpg хранения этих данных в переменной с именем `Get-Content` $photo.</span><span class="sxs-lookup"><span data-stu-id="15d4c-118">The first command in the preceding example uses the `Get-Content` cmdlet to read the contents of the file C:\Photos\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="15d4c-119">Во второй команде командлет Exchange используется для отправки фотографии и крепится к учетной записи пользователя Кена `Set-UserPhoto` Myer.</span><span class="sxs-lookup"><span data-stu-id="15d4c-119">In the second command, the Exchange cmdlet `Set-UserPhoto` is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="15d4c-120">В данном примере в качестве идентификатора учетной записи используется отображаемое имя пользователя Ken Myer в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="15d4c-120">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="15d4c-121">Для ссылки на учетную запись пользователя можно использовать и другие идентификаторы, например, SMTP-адрес пользователя или имя участника-пользователя.</span><span class="sxs-lookup"><span data-stu-id="15d4c-121">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="15d4c-122">Дополнительные сведения см. в документации по Set-UserPhoto. [https://go.microsoft.com/fwlink/p/?LinkId=268536](/powershell/module/exchange/set-userphoto)</span><span class="sxs-lookup"><span data-stu-id="15d4c-122">See the documentation for the Set-UserPhoto cmdlet at [https://go.microsoft.com/fwlink/p/?LinkId=268536](/powershell/module/exchange/set-userphoto) for more information</span></span>
  
<span data-ttu-id="15d4c-p107">Отправка фотографии не означает, что она будет автоматически назначена учетной записи пользователя Ken Myer. После отправки фотография просто будет отображаться в режиме предварительного просмотра на странице параметров Outlook Web App. Чтобы назначить фотографию учетной записи, пользователь должен нажать кнопку **Сохранить** на странице параметров или же администратор должен выполнить третью команду данного примера. В третьей команде используется параметр Save для назначения фотографии учетной записи пользователя Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="15d4c-p107">Uploading the photo does not equate to assigning that photo to Ken Myer's user account. Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page. To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example. That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>
  
```powershell
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="15d4c-127">Чтобы убедиться, что новая фотография назначена учетной записи пользователя, Кен Мойер может войти в Skype для бизнеса, выбрать **параметры,** а затем выбрать My **Picture**.</span><span class="sxs-lookup"><span data-stu-id="15d4c-127">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Skype for Business, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="15d4c-128">В качестве личного фото пользователя Ken Myer должна отобразиться новая фотография.</span><span class="sxs-lookup"><span data-stu-id="15d4c-128">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="15d4c-129">Администратор может проверить фотографию любого пользователя, введя в адресной строке Internet Explorer URL-адрес, подобный показанному ниже.</span><span class="sxs-lookup"><span data-stu-id="15d4c-129">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>
  
```console
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

<span data-ttu-id="15d4c-130">Если администратор может просматривать фотографию с помощью Internet Explorer, но пользователь не может просмотреть его или ее фотографию в Skype для бизнеса, может возникнуть проблема подключения к веб-службам Exchange или службе автообнаружия Exchange.</span><span class="sxs-lookup"><span data-stu-id="15d4c-130">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Skype for Business there may be a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>
  
<span data-ttu-id="15d4c-131">Обратите внимание, что для того, чтобы сделать эту фотографию доступной в Skype для бизнеса, не требуется дополнительная конфигурация.</span><span class="sxs-lookup"><span data-stu-id="15d4c-131">Note, too that no additional configuration is required in order to make this photo available in Skype for Business.</span></span> <span data-ttu-id="15d4c-132">Вместо этого фотография будет мгновенно доступна после загрузки и запуска `Set-UserPhoto` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="15d4c-132">Instead, the photo will be instantly available after it has been uploaded and the `Set-UserPhoto` cmdlet has been run.</span></span>