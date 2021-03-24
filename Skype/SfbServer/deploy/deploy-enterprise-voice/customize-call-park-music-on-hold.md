---
title: Настройка музыки Парка вызовов на удержание вSkype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Настройка музыки Парка вызовов на удержание в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 87dea58d9e339293b047373ac6c44a16bed3bdb3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093047"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a><span data-ttu-id="dd185-103">Настройка музыки Парка вызовов на удержание вSkype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="dd185-103">Customize Call Park music on hold inSkype for Business</span></span>
 
<span data-ttu-id="dd185-104">Настройка музыки Парка вызовов на удержание в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="dd185-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="dd185-105">Вы можете указать собственный музыкальный файл, который можно использовать для удержания музыки, а не музыкальный файл по умолчанию, который используется в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="dd185-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="dd185-106">Чтобы настроить музыку, воспроизводимую при удержании вызова, используйте командлет **Set-CsCallParkServiceMusicOnHoldFile**.</span><span class="sxs-lookup"><span data-stu-id="dd185-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dd185-107">Если вы настраиваете музыку на удержание и хотите, чтобы та же музыка для нескольких сайтов, необходимо настроить музыкальный файл для каждого сайта, который запускает приложение Call Park.</span><span class="sxs-lookup"><span data-stu-id="dd185-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="dd185-108">Чтобы настроить файл музыки, выполните следующие действия</span><span class="sxs-lookup"><span data-stu-id="dd185-108">To customize the music file</span></span>

1. <span data-ttu-id="dd185-109">Войдите на компьютер, на котором установлена оболочка управления Skype для бизнес-серверов в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разрешениях делегирования **установки.**</span><span class="sxs-lookup"><span data-stu-id="dd185-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="dd185-110">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="dd185-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="dd185-111">Выполните команду: </span><span class="sxs-lookup"><span data-stu-id="dd185-111">Run:</span></span>
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="dd185-112">Используйте командлет **Get-CsService** для идентификации службы.</span><span class="sxs-lookup"><span data-stu-id="dd185-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="dd185-113">Подробные сведения [см. в материале Get-CsService.](/powershell/module/skype/get-csservice?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="dd185-113">For details, see [Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="dd185-114">В следующем примере показано, как получить содержимое файла soothingmusic.wma в виде байтового массива и назначить его переменной.</span><span class="sxs-lookup"><span data-stu-id="dd185-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="dd185-115">Затем аудиофайл назначается для режима приостановки вызовов в качестве музыки, воспроизводимой при удержании вызова.</span><span class="sxs-lookup"><span data-stu-id="dd185-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="dd185-116">Подробные сведения см. [в материале Set-CsCallParkServiceMusicOnHoldFile.](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="dd185-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="dd185-117">См. также</span><span class="sxs-lookup"><span data-stu-id="dd185-117">See also</span></span>

[<span data-ttu-id="dd185-118">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="dd185-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="dd185-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="dd185-119">Get-CsService</span></span>](/powershell/module/skype/get-csservice?view=skype-ps)