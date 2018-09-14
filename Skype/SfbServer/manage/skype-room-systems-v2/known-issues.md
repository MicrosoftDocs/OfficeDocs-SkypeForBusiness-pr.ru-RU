---
title: Известные проблемы
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: В этой статье описываются известные проблемы, возникающие v2 Скайп комнаты систем, по функциональным возможностям.
ms.openlocfilehash: 9512403d22d77505c6e2fe4f5160d40537927133
ms.sourcegitcommit: b265545216ff36772d5dc2df381a9046bc71098e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965900"
---
# <a name="known-issues"></a><span data-ttu-id="689af-103">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="689af-103">Known issues</span></span> 
 
<span data-ttu-id="689af-104">В этой статье описаны известные проблемы для версии 2 Скайп комнаты систем, по функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="689af-104">This article lists the known issues for Skype Room Systems v2, by feature area.</span></span>
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<span data-ttu-id="689af-105"><a name="update"> </a></span><span class="sxs-lookup"><span data-stu-id="689af-105"></span></span>  
## <a name="update"></a><span data-ttu-id="689af-106">Обновление</span><span class="sxs-lookup"><span data-stu-id="689af-106">Update</span></span> 

| <span data-ttu-id="689af-107">Название проблемы</span><span class="sxs-lookup"><span data-stu-id="689af-107">Issue title</span></span> |  <span data-ttu-id="689af-108">Поведение \/ Признак</span><span class="sxs-lookup"><span data-stu-id="689af-108">Behavior \/ Symptom</span></span> | <span data-ttu-id="689af-109">Известный обходной путь</span><span class="sxs-lookup"><span data-stu-id="689af-109">Known workaround</span></span> | <span data-ttu-id="689af-110">Статья БАЗЫ знаний</span><span class="sxs-lookup"><span data-stu-id="689af-110">KB Article</span></span> |
|  ---        |      ---             |   ---            | --- |
|  <span data-ttu-id="689af-111">Устаревший приложения</span><span class="sxs-lookup"><span data-stu-id="689af-111">App out of date</span></span>         |    <span data-ttu-id="689af-112">Ошибка «устаревший конфигурации системы» отображается консоль версии 2 Скайп комнаты систем.</span><span class="sxs-lookup"><span data-stu-id="689af-112">The Skype Room Systems v2 console shows a "system config out of date" error.</span></span>                |   [<span data-ttu-id="689af-113">С помощью средства восстановления системы комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="689af-113">Use the Skype Room Systems v2 recovery tool</span></span>](recovery-tool.md)             |  <span data-ttu-id="689af-114">Нет</span><span class="sxs-lookup"><span data-stu-id="689af-114">None</span></span> |


<span data-ttu-id="689af-115"><a name="OS-conflicts"> </a></span><span class="sxs-lookup"><span data-stu-id="689af-115"></span></span>  
## <a name="user-interface"></a><span data-ttu-id="689af-116">Пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="689af-116">User interface</span></span> 

| <span data-ttu-id="689af-117">Название проблемы</span><span class="sxs-lookup"><span data-stu-id="689af-117">Issue title</span></span> |  <span data-ttu-id="689af-118">Поведение \/ Признак</span><span class="sxs-lookup"><span data-stu-id="689af-118">Behavior \/ Symptom</span></span> | <span data-ttu-id="689af-119">Известный обходной путь</span><span class="sxs-lookup"><span data-stu-id="689af-119">Known workaround</span></span> | <span data-ttu-id="689af-120">Статья БАЗЫ знаний</span><span class="sxs-lookup"><span data-stu-id="689af-120">KB Article</span></span> |
|  ---        |      ---             |   ---            | --- |
|<span data-ttu-id="689af-121">Отсутствует виртуальной клавиатуры</span><span class="sxs-lookup"><span data-stu-id="689af-121">Virtual keyboard missing</span></span>   | <span data-ttu-id="689af-122">Виртуальная клавиатура не появляется при следует ввести сведения в системах комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="689af-122">The virtual keyboard doesn't appear when you need to enter information in Skype Room Systems v2.</span></span> <span data-ttu-id="689af-123">Эта проблема возникает после установки обновления создателей 10 (версия 1703) на 4 Surface Pro, на котором выполняется систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="689af-123">This issue occurs after the Windows 10 Creators Update (version 1703) is installed on the Surface Pro 4 on which Skype Room Systems v2 is running.</span></span> | <span data-ttu-id="689af-124">Чтобы обойти эту проблему, вручную откройте виртуальной клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="689af-124">To work around this issue, manually open the virtual keyboard.</span></span> <span data-ttu-id="689af-125">Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="689af-125">To do this, follow these steps:</span></span><br><br> <span data-ttu-id="689af-126">**1.** нажмите кнопку «» и хранение на панели задач и нажмите кнопку **Показать сенсорной клавиатуры** .</span><span class="sxs-lookup"><span data-stu-id="689af-126">**1.** Tap and hold the task bar, and then tap **Show touch keyboard** button.</span></span> <span data-ttu-id="689af-127">В правой части панели задач появляется значок Клавиатура.</span><span class="sxs-lookup"><span data-stu-id="689af-127">A keyboard icon should appear on the right side of the task bar.</span></span> <br><br> <span data-ttu-id="689af-128">**2.** нажмите значок клавиатуры, чтобы открыть виртуальной клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="689af-128">**2.** Tap the keyboard icon to open the virtual keyboard.</span></span> | [<span data-ttu-id="689af-129">KB4037694</span><span class="sxs-lookup"><span data-stu-id="689af-129">KB4037694</span></span>](https://support.microsoft.com/en-us/help/4037694/virtual-keyboard-missing-in-skype-room-systems-v2) | 
   

<span data-ttu-id="689af-130"><a name="Hardware"> </a></span><span class="sxs-lookup"><span data-stu-id="689af-130"></span></span>  
## <a name="hardware"></a><span data-ttu-id="689af-131">Оборудование</span><span class="sxs-lookup"><span data-stu-id="689af-131">Hardware</span></span>

| <span data-ttu-id="689af-132">Название проблемы</span><span class="sxs-lookup"><span data-stu-id="689af-132">Issue title</span></span> |  <span data-ttu-id="689af-133">Поведение \/ Признак</span><span class="sxs-lookup"><span data-stu-id="689af-133">Behavior \/ Symptom</span></span> | <span data-ttu-id="689af-134">Известный обходной путь</span><span class="sxs-lookup"><span data-stu-id="689af-134">Known workaround</span></span> | <span data-ttu-id="689af-135">Статья БАЗЫ знаний</span><span class="sxs-lookup"><span data-stu-id="689af-135">KB Article</span></span> |
|  ---        |      ---             |   ---            |   --- |
| <span data-ttu-id="689af-136">Не обнаружено мониторов</span><span class="sxs-lookup"><span data-stu-id="689af-136">Monitors not detected</span></span> | <span data-ttu-id="689af-137">При запуске системы комнаты Скайп версии 2 на устройстве Surface Pro (модель 2017) не распознаются мониторов.</span><span class="sxs-lookup"><span data-stu-id="689af-137">When you run Skype Room Systems v2 on a Surface Pro (Model 2017) device, monitors are not detected.</span></span> |  <span data-ttu-id="689af-138">Нажмите и удерживайте клавишу Surface Pro кнопки питания 20 или несколько секунд.</span><span class="sxs-lookup"><span data-stu-id="689af-138">Hold down the Surface Pro power button for 20 or more seconds.</span></span> <span data-ttu-id="689af-139">При этом устройство перезагрузки и очищает кэш графики.</span><span class="sxs-lookup"><span data-stu-id="689af-139">When you do this, the device restarts and clears the graphics cache.</span></span> |[<span data-ttu-id="689af-140">KB4055681</span><span class="sxs-lookup"><span data-stu-id="689af-140">KB4055681</span></span>](https://support.microsoft.com/en-us/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 
          
<span data-ttu-id="689af-141"><a name="Limits"> </a></span><span class="sxs-lookup"><span data-stu-id="689af-141"></span></span>
## <a name="limitations-and-expected-behaviors"></a><span data-ttu-id="689af-142">Ограничения и предполагаемое поведение</span><span class="sxs-lookup"><span data-stu-id="689af-142">Limitations and expected behaviors</span></span>
***
<span data-ttu-id="689af-143">Версии 2 не поддерживает ввод HDCP, что наблюдалась вызвать проблемы с HDMI систем комнаты Скайп потребления функциональные возможности (видео).</span><span class="sxs-lookup"><span data-stu-id="689af-143">Skype Room Systems v2 does not support HDCP input, which has been observed to cause issues with HDMI ingest functionality (video, audio).</span></span> <span data-ttu-id="689af-144">Будьте внимательны для обеспечения отключите параметры HDCP коммутаторы, подключенных к версии 2 Скайп комнаты систем.</span><span class="sxs-lookup"><span data-stu-id="689af-144">Take care to ensure that switches connected to Skype Room Systems v2 have HDCP options turned off.</span></span> 
***
<span data-ttu-id="689af-145">Бытовой телевизор, используемый в качестве центрального дисплея, должен поддерживать функцию управления бытовой электронной техникой (CEC) стандарта HDMI для автоматического переключения на активный источник видеосигнала из режима ожидания.</span><span class="sxs-lookup"><span data-stu-id="689af-145">A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode.</span></span> <span data-ttu-id="689af-146">Эту функцию поддерживают не все телевизоры.</span><span class="sxs-lookup"><span data-stu-id="689af-146">This feature is not supported on all TVs.</span></span> 
***
<span data-ttu-id="689af-147">Всегда используйте подключения проводной сети 1 Гбит/с, чтобы убедиться, что у вас необходимые пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="689af-147">Always use a wired 1 Gbps network connection to assure you will have the needed bandwidth.</span></span> 
***
<span data-ttu-id="689af-148">Если устройство v2 систем комнаты Скайп теряет отношение доверия с домена (например, если удалить v2 систем комнаты Скайп из домена после его присоединен к домену), нельзя будет для проверки подлинности в устройство и откройте копирование параметров.</span><span class="sxs-lookup"><span data-stu-id="689af-148">If your Skype Room Systems v2 device loses trust with the domain (for example, if you remove the Skype Room Systems v2 from the domain after it is domain joined), you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="689af-149">Обходным решением является вход с использованием учетной записи локального администратора.</span><span class="sxs-lookup"><span data-stu-id="689af-149">The workaround is to log in with the local Admin account.</span></span> 
***
<span data-ttu-id="689af-150">64-разрядная версия Windows 10 Enterprise Годовщина выпуска (английский язык, версия 1607) больше не поддерживается по состоянию на версии 2 систем комнаты Скайп 3.0.12.0.</span><span class="sxs-lookup"><span data-stu-id="689af-150">The 64-bit version of Windows 10 Enterprise Anniversary edition (English language, version 1607) is no longer supported as of Skype Room Systems v2 release 3.0.12.0.</span></span> 
***

<span data-ttu-id="689af-151"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="689af-151"></span></span>  
## <a name="see-also"></a><span data-ttu-id="689af-152">Были ли эти инструкции полезны? Если да, укажите это в конце статьи. Если нет, сообщите нам о недочетах, и мы постараемся найти решение.</span><span class="sxs-lookup"><span data-stu-id="689af-152">See also</span></span>

[<span data-ttu-id="689af-153">Справка по версии 2 Скайп комнаты систем</span><span class="sxs-lookup"><span data-stu-id="689af-153">Skype Room Systems version 2 help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="689af-154">Управление Системами комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="689af-154">Manage Skype Room Systems v2</span></span>](skype-room-systems-v2.md)