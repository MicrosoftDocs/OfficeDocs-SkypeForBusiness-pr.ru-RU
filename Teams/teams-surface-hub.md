---
title: Развертывание групп Майкрософт для предоставления сервера-концентратора
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 09/26/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Настройка параметров администрирования для групп Майкрософт для сервера-концентратора поверхности.
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 62eb0e6fbae734a83fd96f89203db0547938e9d3
ms.sourcegitcommit: 7f721d89559831de2cf1495feb0fc57b22b77d78
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "25018588"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="c25cd-103">Развертывание групп Майкрософт для предоставления сервера-концентратора</span><span class="sxs-lookup"><span data-stu-id="c25cd-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="c25cd-104">Перед развертыванием группами Майкрософт для сервера-концентратора Microsoft Surface убедитесь, что удовлетворены оборудования, операционной системы и другие требования.</span><span class="sxs-lookup"><span data-stu-id="c25cd-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="c25cd-105">Дополнительные сведения можно найти в [руководстве администратора сервера-концентратора Microsoft Surface](https://docs.microsoft.com/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="c25cd-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/surface-hub/).</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="c25cd-106">Установка группы для предоставления концентратора из хранилища Microsoft</span><span class="sxs-lookup"><span data-stu-id="c25cd-106">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="c25cd-107">Эти инструкции предназначены для установки групп для сервера-концентратора поверхность из хранилища Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c25cd-107">These instructions are for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="c25cd-108">Запустите хранилища Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="c25cd-108">Start the Microsoft Store:</span></span><br>
   <span data-ttu-id="c25cd-109">а.</span><span class="sxs-lookup"><span data-stu-id="c25cd-109">a.</span></span> <span data-ttu-id="c25cd-110">Коснитесь кнопки **Пуск** > **все приложения** > **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="c25cd-110">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="c25cd-111">б.</span><span class="sxs-lookup"><span data-stu-id="c25cd-111">b.</span></span> <span data-ttu-id="c25cd-112">Коснитесь **устройства сервера-концентратора поверхность учетная запись, управление**.</span><span class="sxs-lookup"><span data-stu-id="c25cd-112">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="c25cd-113">в.</span><span class="sxs-lookup"><span data-stu-id="c25cd-113">c.</span></span> <span data-ttu-id="c25cd-114">В левой части перейдите на вкладку **приложений и компонентов** .</span><span class="sxs-lookup"><span data-stu-id="c25cd-114">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="c25cd-115">г.</span><span class="sxs-lookup"><span data-stu-id="c25cd-115">d.</span></span> <span data-ttu-id="c25cd-116">В правой части окна нажмите кнопку **Открыть хранилище** .</span><span class="sxs-lookup"><span data-stu-id="c25cd-116">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="c25cd-117">Из магазина Microsoft поиск *Групп Майкрософт*.</span><span class="sxs-lookup"><span data-stu-id="c25cd-117">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="c25cd-118">Отображается **Группами Майкрософт для сервера-концентратора поверхности** .</span><span class="sxs-lookup"><span data-stu-id="c25cd-118">The **Microsoft Teams for Surface Hub** will be displayed.</span></span> <span data-ttu-id="c25cd-119">Нажмите кнопку **получить приложение** для установки.</span><span class="sxs-lookup"><span data-stu-id="c25cd-119">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="c25cd-120">После завершения установки перезапустите сервер-концентратор поверхности.</span><span class="sxs-lookup"><span data-stu-id="c25cd-120">When the installation is complete, restart the Surface Hub.</span></span> 

> [!NOTE]
> <span data-ttu-id="c25cd-121">Не коснитесь на **Запуск** из магазина страницы.</span><span class="sxs-lookup"><span data-stu-id="c25cd-121">Do not tap on **Launch** from the Store listing page.</span></span>

## <a name="make-teams-the-default-calling-and-meetings-application"></a><span data-ttu-id="c25cd-122">Создание групп по умолчанию звонков и собраний приложения</span><span class="sxs-lookup"><span data-stu-id="c25cd-122">Make Teams the default calling and meetings application</span></span>
 
<span data-ttu-id="c25cd-123">Существует два варианта для настройки политики по умолчанию звонков и собраний приложения.</span><span class="sxs-lookup"><span data-stu-id="c25cd-123">There are two options for configuring the default calling and meetings application policy:</span></span> 

- <span data-ttu-id="c25cd-124">**Вариант 1**: настройте с помощью USB-ключ.</span><span class="sxs-lookup"><span data-stu-id="c25cd-124">**Option 1**: Configure via USB key.</span></span> 
- <span data-ttu-id="c25cd-125">**Вариант 2**: настройка с помощью MDM, такие как Intune.</span><span class="sxs-lookup"><span data-stu-id="c25cd-125">**Option 2**: Configure via MDM such as Intune.</span></span>
 
### <a name="option-1-configure-via-usb-key"></a><span data-ttu-id="c25cd-126">Вариант 1: Настройте с помощью USB-ключ</span><span class="sxs-lookup"><span data-stu-id="c25cd-126">Option 1: Configure via USB key</span></span> 
 
<span data-ttu-id="c25cd-127">Пакеты можно найти на этой [странице загрузки](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span><span class="sxs-lookup"><span data-stu-id="c25cd-127">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="c25cd-128">Выберите один для пакета, который планируется установить и скопируйте его на USB.</span><span class="sxs-lookup"><span data-stu-id="c25cd-128">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="c25cd-129">Правильный .ppkg файл, используемый зависит от приложения политику по умолчанию, которое вы хотите применить следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c25cd-129">The correct .ppkg file to use depends on the default application policy you'd like to apply as follows:</span></span> 

|<span data-ttu-id="c25cd-130">Число</span><span class="sxs-lookup"><span data-stu-id="c25cd-130">Number</span></span>  |<span data-ttu-id="c25cd-131">Описание</span><span class="sxs-lookup"><span data-stu-id="c25cd-131">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="c25cd-132">0</span><span class="sxs-lookup"><span data-stu-id="c25cd-132">0</span></span>     | <span data-ttu-id="c25cd-133">Предпочитаемый приложения Скайп на начальном экране, доступные команды собраний</span><span class="sxs-lookup"><span data-stu-id="c25cd-133">Skype preferred app on the Start Screen, Teams Meetings available</span></span>        |
|<span data-ttu-id="c25cd-134">1</span><span class="sxs-lookup"><span data-stu-id="c25cd-134">1</span></span>     | <span data-ttu-id="c25cd-135">Предпочитаемый приложения группы на начальном экране, доступные Скайп собраний</span><span class="sxs-lookup"><span data-stu-id="c25cd-135">Teams preferred app on the Start Screen, Skype Meetings available</span></span>        |
|<span data-ttu-id="c25cd-136">2</span><span class="sxs-lookup"><span data-stu-id="c25cd-136">2</span></span>     | <span data-ttu-id="c25cd-137">Команды исключительных приложения на начальном экране (недоступно приложение Скайп)</span><span class="sxs-lookup"><span data-stu-id="c25cd-137">Teams exclusive app on the Start screen (Skype app not available)</span></span>        |
 
1. <span data-ttu-id="c25cd-138">Присоедините USB-ключ устройство поверхность сервера-концентратора.</span><span class="sxs-lookup"><span data-stu-id="c25cd-138">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="c25cd-139">Откройте **Параметры** приложения на устройстве поверхность сервера-концентратора.</span><span class="sxs-lookup"><span data-stu-id="c25cd-139">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="c25cd-140">Откройте **Управление учетными записями устройства контактной сервера-концентратора**.</span><span class="sxs-lookup"><span data-stu-id="c25cd-140">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="c25cd-141">Откройте **Управление устройствами**.</span><span class="sxs-lookup"><span data-stu-id="c25cd-141">Open **Device Management**.</span></span> 
5. <span data-ttu-id="c25cd-142">Нажмите кнопку **Добавить или удалить подготовки пакета**.</span><span class="sxs-lookup"><span data-stu-id="c25cd-142">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="c25cd-143">Нажмите кнопку **добавить пакет**.</span><span class="sxs-lookup"><span data-stu-id="c25cd-143">Click **Add Package**.</span></span>
7. <span data-ttu-id="c25cd-144">В раскрывающемся меню выберите параметр **Съемный носитель** .</span><span class="sxs-lookup"><span data-stu-id="c25cd-144">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="c25cd-145">Добавьте соответствующие **TeamsRTMMode\*.ppkg** пакет, который ранее был скопирован на ключ USB.</span><span class="sxs-lookup"><span data-stu-id="c25cd-145">Add the appropriate **TeamsRTMMode\*.ppkg** package that was previously copied to the USB key.</span></span> 
9. <span data-ttu-id="c25cd-146">Перезагрузите устройство поверхность сервера-концентратора.</span><span class="sxs-lookup"><span data-stu-id="c25cd-146">Restart the Surface Hub device.</span></span> 
10. <span data-ttu-id="c25cd-147">После перезагрузки устройства, должна появиться возможность запуска приложения группы на начальном экране и присоединиться к собранию из календаря.</span><span class="sxs-lookup"><span data-stu-id="c25cd-147">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span> 

### <a name="option-2-configure-via-mdm-such-as-intune"></a><span data-ttu-id="c25cd-148">Вариант 2: Настройка с помощью MDM, такие как Intune</span><span class="sxs-lookup"><span data-stu-id="c25cd-148">Option 2: Configure via MDM such as Intune</span></span> 

<span data-ttu-id="c25cd-149">Используйте следующие для настройки политики по умолчанию звонков и собраний приложения с помощью Intune.</span><span class="sxs-lookup"><span data-stu-id="c25cd-149">Use the following to configure the default calling and meetings application policy via Intune.</span></span> <span data-ttu-id="c25cd-150">Также можно найти, [развертывание групп Майкрософт для сервера-концентратора поверхность приложение, использующее Intune](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/).</span><span class="sxs-lookup"><span data-stu-id="c25cd-150">Also see the blog, [Deploy the Microsoft Teams for Surface Hub app using Intune](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/).</span></span>

|<span data-ttu-id="c25cd-151">Параметр</span><span class="sxs-lookup"><span data-stu-id="c25cd-151">Setting</span></span>   |<span data-ttu-id="c25cd-152">Значение</span><span class="sxs-lookup"><span data-stu-id="c25cd-152">Value</span></span>    |<span data-ttu-id="c25cd-153">Описание</span><span class="sxs-lookup"><span data-stu-id="c25cd-153">Description</span></span>    |
|----------|---------|---------|
|<span data-ttu-id="c25cd-154">Путь</span><span class="sxs-lookup"><span data-stu-id="c25cd-154">Path</span></span>      | <span data-ttu-id="c25cd-155">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span><span class="sxs-lookup"><span data-stu-id="c25cd-155">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span></span>        |
|<span data-ttu-id="c25cd-156">Тип данных</span><span class="sxs-lookup"><span data-stu-id="c25cd-156">Data Type</span></span> | <span data-ttu-id="c25cd-157">целое число (0-2)</span><span class="sxs-lookup"><span data-stu-id="c25cd-157">integer (0-2)</span></span>   |<span data-ttu-id="c25cd-158">0 — Скайп предпочитаемый приложения на начальном экране, доступные команды собраний</span><span class="sxs-lookup"><span data-stu-id="c25cd-158">0 - Skype preferred app on the Start Screen, Teams Meetings available</span></span><br><span data-ttu-id="c25cd-159">1 - предпочитаемый приложения группы на начальном экране, доступные Скайп собраний</span><span class="sxs-lookup"><span data-stu-id="c25cd-159">1 - Teams preferred app on the Start Screen, Skype Meetings available</span></span><br><span data-ttu-id="c25cd-160">2 - группам исключительных приложения на начальном экране (недоступно приложение Скайп)</span><span class="sxs-lookup"><span data-stu-id="c25cd-160">2 - Teams exclusive app on the Start screen (Skype app not available)</span></span> |
|<span data-ttu-id="c25cd-161">Операции</span><span class="sxs-lookup"><span data-stu-id="c25cd-161">Operations</span></span>| <span data-ttu-id="c25cd-162">Получение, установка</span><span class="sxs-lookup"><span data-stu-id="c25cd-162">Get, Set</span></span>        |

|<span data-ttu-id="c25cd-163">Параметр</span><span class="sxs-lookup"><span data-stu-id="c25cd-163">Setting</span></span>   |<span data-ttu-id="c25cd-164">Значение</span><span class="sxs-lookup"><span data-stu-id="c25cd-164">Value</span></span>    |
|----------|---------|
|<span data-ttu-id="c25cd-165">Путь</span><span class="sxs-lookup"><span data-stu-id="c25cd-165">Path</span></span>      | <span data-ttu-id="c25cd-166">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span><span class="sxs-lookup"><span data-stu-id="c25cd-166">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span></span>        |
|<span data-ttu-id="c25cd-167">Тип данных</span><span class="sxs-lookup"><span data-stu-id="c25cd-167">Data Type</span></span> | <span data-ttu-id="c25cd-168">Строка — строка набора к группам код пакета приложения как **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! Группы**</span><span class="sxs-lookup"><span data-stu-id="c25cd-168">string - set string to Teams application package ID as **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams**</span></span> |
|<span data-ttu-id="c25cd-169">Операции</span><span class="sxs-lookup"><span data-stu-id="c25cd-169">Operations</span></span>| <span data-ttu-id="c25cd-170">Получение, установка</span><span class="sxs-lookup"><span data-stu-id="c25cd-170">Get, Set</span></span>        |

<span data-ttu-id="c25cd-171">Перезагрузите устройство поверхность сервера-концентратора.</span><span class="sxs-lookup"><span data-stu-id="c25cd-171">Restart the Surface Hub device.</span></span> <span data-ttu-id="c25cd-172">После перезагрузки устройства, должна появиться возможность запуска приложения группы на начальном экране и присоединиться к собранию из календаря.</span><span class="sxs-lookup"><span data-stu-id="c25cd-172">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span>

