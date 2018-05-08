---
title: Настройка функции воспроизведения музыки для режима удержания при парковке вызова в Skype для бизнеса 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Настройка парковки вызовов, музыки на хранение в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 95e332aad7d96c366cfc73ca1bcf3f289b5f14ab
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="customize-call-park-music-on-hold-inskype-for-business-2015"></a><span data-ttu-id="dc37b-103">Настройка функции воспроизведения музыки для режима удержания при парковке вызова в Skype для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="dc37b-103">Customize Call Park music on hold inSkype for Business 2015</span></span>
 
<span data-ttu-id="dc37b-104">Настройка парковки вызовов, музыки на хранение в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="dc37b-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="dc37b-105">Можно указать собственный файл музыки для использования при удержании, вместо файлов музыку по умолчанию, которое поставляется с Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="dc37b-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="dc37b-106">Чтобы настроить музыку при удержании, используйте командлет **Set-CsCallParkServiceMusicOnHoldFile** .</span><span class="sxs-lookup"><span data-stu-id="dc37b-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dc37b-107">Если настроить музыку при удержании и должно же музыки для нескольких сайтов, необходимо настроить файл музыки для каждого сайта, на котором выполняется приложение парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="dc37b-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="dc37b-108">Чтобы настроить файл музыки, выполните следующие действия</span><span class="sxs-lookup"><span data-stu-id="dc37b-108">To customize the music file</span></span>

1. <span data-ttu-id="dc37b-109">Войдите на компьютер, где установлена Скайп для консоли Business Server как член группы RTCUniversalServerAdmins или с необходимые права пользователя как описано в **Делегирование разрешений на установку**.</span><span class="sxs-lookup"><span data-stu-id="dc37b-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="dc37b-110">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="dc37b-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="dc37b-111">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="dc37b-111">Run:</span></span>
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="dc37b-112">Командлет **Get-CsService** для идентификации службы.</span><span class="sxs-lookup"><span data-stu-id="dc37b-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="dc37b-113">Дополнительные сведения см [Командлет Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="dc37b-113">For details, see [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="dc37b-114">В следующем примере показано, как получить содержимое файла soothingmusic.wma в виде байтового массива и назначить его переменной.</span><span class="sxs-lookup"><span data-stu-id="dc37b-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="dc37b-115">Затем аудиофайл назначается для режима приостановки вызовов в качестве музыки, воспроизводимой при удержании вызова.</span><span class="sxs-lookup"><span data-stu-id="dc37b-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="dc37b-116">Дополнительные сведения см [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="dc37b-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="dc37b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="dc37b-117">See also</span></span>

#### 

[<span data-ttu-id="dc37b-118">SET-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="dc37b-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="dc37b-119">Командлет Get-CsService</span><span class="sxs-lookup"><span data-stu-id="dc37b-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)

