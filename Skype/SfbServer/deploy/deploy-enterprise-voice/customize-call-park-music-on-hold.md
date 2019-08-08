---
title: Настройка музыкального сопровождения для приема звонков на удержание в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Настройка музыкального сопровождения для остановки звонка на удержании в корпоративной голосовой связи Skype для бизнеса Server.
ms.openlocfilehash: 834e6e811637c120e675a674f51ac0edeaf90542
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245629"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a><span data-ttu-id="0af6a-103">Настройка музыкального сопровождения для приема звонков на удержание в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0af6a-103">Customize Call Park music on hold inSkype for Business</span></span>
 
<span data-ttu-id="0af6a-104">Настройка музыкального сопровождения для остановки звонка на удержании в корпоративной голосовой связи Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0af6a-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="0af6a-105">Вы можете указать свой музыкальный файл, который будет использоваться для сохранения музыки, вместо музыкального файла по умолчанию, который входит в состав Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0af6a-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="0af6a-106">Чтобы настроить музыку, воспроизводимую при удержании вызова, используйте командлет **Set-CsCallParkServiceMusicOnHoldFile**.</span><span class="sxs-lookup"><span data-stu-id="0af6a-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0af6a-107">Если вы настроите музыку на удержании и хотите использовать одну и ту же музыку для нескольких сайтов, необходимо настроить музыкальный файл для каждого сайта, на котором запущено приложение для парковки звонков.</span><span class="sxs-lookup"><span data-stu-id="0af6a-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="0af6a-108">Чтобы настроить файл музыки, выполните следующие действия</span><span class="sxs-lookup"><span data-stu-id="0af6a-108">To customize the music file</span></span>

1. <span data-ttu-id="0af6a-109">Войдите в систему на компьютере, на котором установлена консоль управления Skype для бизнеса Server, в качестве участника группы Рткуниверсалсерверадминс или с необходимыми правами пользователя, описанными в разделе **Делегирование разрешений на настройку**.</span><span class="sxs-lookup"><span data-stu-id="0af6a-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="0af6a-110">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="0af6a-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0af6a-111">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0af6a-111">Run:</span></span>
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="0af6a-112">Используйте командлет **Get-CsService** для идентификации службы.</span><span class="sxs-lookup"><span data-stu-id="0af6a-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="0af6a-113">Подробности можно найти в [статьях Get-кссервице](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0af6a-113">For details, see [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="0af6a-114">В следующем примере показано, как получить содержимое файла soothingmusic.wma в виде байтового массива и назначить его переменной.</span><span class="sxs-lookup"><span data-stu-id="0af6a-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="0af6a-115">Затем аудиофайл назначается для режима приостановки вызовов в качестве музыки, воспроизводимой при удержании вызова.</span><span class="sxs-lookup"><span data-stu-id="0af6a-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="0af6a-116">Подробности можно найти в разделе [Set-кскаллпарксервицемусиконхолдфиле](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0af6a-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="0af6a-117">См. также</span><span class="sxs-lookup"><span data-stu-id="0af6a-117">See also</span></span>

[<span data-ttu-id="0af6a-118">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="0af6a-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="0af6a-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="0af6a-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
