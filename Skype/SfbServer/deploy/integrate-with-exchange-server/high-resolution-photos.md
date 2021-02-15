---
title: Настройка использования фотографий высокого разрешения в Skype для бизнеса Server
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
description: Сводка. Настройка использования фотографий высокого разрешения в Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 или Exchange Online и Skype для бизнеса Server.
ms.openlocfilehash: c55e5a90e222ea024dd63f72b26627141b2f113e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834009"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a><span data-ttu-id="05784-103">Настройка использования фотографий высокого разрешения в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="05784-103">Configure the use of high-resolution photos in Skype for Business Server</span></span>
 
<span data-ttu-id="05784-104">**Сводка:** Настройка использования фотографий высокого разрешения в Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 или Exchange Online и Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="05784-104">**Summary:** Configure the use of high-resolution photos in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013, or Exchange Online and Skype for Business Server.</span></span>
  
<span data-ttu-id="05784-105">В Skype для бизнеса Server фотографии можно хранить в почтовом ящике пользователя Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 или Exchange Online, что позволяет фотографии размером до 648 пикселей на 648 пикселей.</span><span class="sxs-lookup"><span data-stu-id="05784-105">In Skype for Business Server, photos can be stored in a user's Exchange Server 2019, Exchange Server 2016, Exchange Server 2013, or Exchange Online mailbox, which allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="05784-106">Кроме того, Exchange Server могут автоматически по мере необходимости реанимировать эти фотографии для использования в разных продуктах.</span><span class="sxs-lookup"><span data-stu-id="05784-106">In addition, Exchange Server can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="05784-107">Как правило, используются фотографии трех размеров и разрешений, которые перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="05784-107">Typically that means three different photo sizes and resolutions:</span></span>
  
- <span data-ttu-id="05784-108">Размер 64 пикселя на 64 пикселя— размер, используемый для атрибута thumbnailPhoto Active Directory.</span><span class="sxs-lookup"><span data-stu-id="05784-108">64 pixels by 64 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="05784-109">Если вы загрузите фотографию в Exchange Server, Exchange автоматически создаст версию этой фотографии размером 64 на 64 пикселя и обнодит атрибут thumbnailPhoto пользователя.</span><span class="sxs-lookup"><span data-stu-id="05784-109">If you upload a photo to Exchange Server, Exchange will automatically create a 64 pixel by 64 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="05784-110">Обратите внимание, что обратное не так: если вручную обновить атрибут thumbnailPhoto в Active Directory, фотография в почтовом ящике Exchange пользователя не будет автоматически обновляться.</span><span class="sxs-lookup"><span data-stu-id="05784-110">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange mailbox will not automatically be updated.</span></span>
    
- <span data-ttu-id="05784-111">96 пикселей по 96 пикселей для использования в Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype для бизнеса Web App и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="05784-111">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App, and Skype for Business.</span></span>
    
- <span data-ttu-id="05784-112">648 пикселей на 648 пикселей для использования в Skype для бизнеса и Skype для бизнеса Web App Skype для бизнеса Web App.</span><span class="sxs-lookup"><span data-stu-id="05784-112">648 pixels by 648 pixels for use in Skype for Business and Skype for Business Web App Skype for Business Web App.</span></span>
    
> [!NOTE]
> <span data-ttu-id="05784-113">Если у вас есть ресурсы, рекомендуется отправить 648 фотографий x 648; обеспечивает максимальное разрешение и оптимальное качество изображения в любом из приложений Office 2013.</span><span class="sxs-lookup"><span data-stu-id="05784-113">If you have the resources, it is recommended that you upload 648 x 648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications.</span></span> <span data-ttu-id="05784-114">Каждая фотография JPEG размером 648 x 648 и глубиной 24 бита приводит к размеру файла примерно 240 килобайт.</span><span class="sxs-lookup"><span data-stu-id="05784-114">Each JPEG photo with a size of 648 x 648 and a depth of 24 bits results in a file size of approximately 240 kilobytes.</span></span> <span data-ttu-id="05784-115">Это значит, что для каждых 4 пользовательских фотографий потребуется примерно 1 мегабайт дискового пространства.</span><span class="sxs-lookup"><span data-stu-id="05784-115">That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span> 
  
<span data-ttu-id="05784-116">Фотографии высокого разрешения, доступ к которым можно получить с помощью веб-служб Exchange, могут загружать пользователи, работающие с Outlook 2013 Web App; пользователям разрешено обновлять только собственные фотографии.</span><span class="sxs-lookup"><span data-stu-id="05784-116">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="05784-117">Администраторы, однако, могут обновить фотографию для любого пользователя с помощью командной Windows PowerShell Exchange и следующих команд:</span><span class="sxs-lookup"><span data-stu-id="05784-117">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>
  
```powershell
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="05784-118">Первая команда в предыдущем примере использует командлет для чтения содержимого файла C:\Photos\Kenmyer.jpg и хранения этих данных в переменной с именем `Get-Content` $photo.</span><span class="sxs-lookup"><span data-stu-id="05784-118">The first command in the preceding example uses the `Get-Content` cmdlet to read the contents of the file C:\Photos\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="05784-119">Во второй команде командлет Exchange используется для отправки фотографии и прикрепления этой фотографии к учетной записи `Set-UserPhoto` пользователя Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="05784-119">In the second command, the Exchange cmdlet `Set-UserPhoto` is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="05784-120">В данном примере в качестве идентификатора учетной записи используется отображаемое имя пользователя Ken Myer в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="05784-120">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="05784-121">Для ссылки на учетную запись пользователя можно использовать и другие идентификаторы, например, SMTP-адрес пользователя или имя участника-пользователя.</span><span class="sxs-lookup"><span data-stu-id="05784-121">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="05784-122">Дополнительные сведения см. в документации по Set-UserPhoto [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) управления</span><span class="sxs-lookup"><span data-stu-id="05784-122">See the documentation for the Set-UserPhoto cmdlet at [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) for more information</span></span>
  
<span data-ttu-id="05784-p107">Отправка фотографии не означает, что она будет автоматически назначена учетной записи пользователя Ken Myer. После отправки фотография просто будет отображаться в режиме предварительного просмотра на странице параметров Outlook Web App. Чтобы назначить фотографию учетной записи, пользователь должен нажать кнопку **Сохранить** на странице параметров или же администратор должен выполнить третью команду данного примера. В третьей команде используется параметр Save для назначения фотографии учетной записи пользователя Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="05784-p107">Uploading the photo does not equate to assigning that photo to Ken Myer's user account. Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page. To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example. That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>
  
```powershell
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="05784-127">Чтобы убедиться, что новая фотография назначена учетной записи пользователя, Пользователь Ken Myer может войти в Skype для бизнеса, выбрать "Параметры" и выбрать **"Мой рисунок".**</span><span class="sxs-lookup"><span data-stu-id="05784-127">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Skype for Business, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="05784-128">В качестве личного фото пользователя Ken Myer должна отобразиться новая фотография.</span><span class="sxs-lookup"><span data-stu-id="05784-128">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="05784-129">Администратор может проверить фотографию любого пользователя, введя в адресной строке Internet Explorer URL-адрес, подобный показанному ниже.</span><span class="sxs-lookup"><span data-stu-id="05784-129">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>
  
```console
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

<span data-ttu-id="05784-130">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Skype for Business there may be a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span><span class="sxs-lookup"><span data-stu-id="05784-130">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Skype for Business there may be a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>
  
<span data-ttu-id="05784-131">Обратите внимание, что для того, чтобы сделать фотографию доступной в Skype для бизнеса, не требуется дополнительная настройка.</span><span class="sxs-lookup"><span data-stu-id="05784-131">Note, too that no additional configuration is required in order to make this photo available in Skype for Business.</span></span> <span data-ttu-id="05784-132">Вместо этого фотография мгновенно станет доступна после ее отправки и запуска `Set-UserPhoto` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="05784-132">Instead, the photo will be instantly available after it has been uploaded and the `Set-UserPhoto` cmdlet has been run.</span></span>
