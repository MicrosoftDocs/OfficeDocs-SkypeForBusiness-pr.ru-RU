---
title: Развертывание групп Майкрософт для предоставления сервера-концентратора
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
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
ms.openlocfilehash: 485e4063c523608421955b86e0be680d5dc10b9a
ms.sourcegitcommit: 5742301cdd28e5e26107920f18e70f41b0f67cfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2018
ms.locfileid: "27132005"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="6ceeb-103">Развертывание групп Майкрософт для предоставления сервера-концентратора</span><span class="sxs-lookup"><span data-stu-id="6ceeb-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="6ceeb-104">Перед развертыванием группами Майкрософт для сервера-концентратора Microsoft Surface убедитесь, что удовлетворены оборудования, операционной системы и другие требования.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="6ceeb-105">Дополнительные сведения можно найти в [руководстве администратора сервера-концентратора Microsoft Surface](https://docs.microsoft.com/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="6ceeb-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/surface-hub/).</span></span>

> [!NOTE]
> <span data-ttu-id="6ceeb-106">Если переход от Скайп для бизнеса в Интернет, необходимо подтвердить, что лицензия группами Майкрософт назначенных пользователю.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-106">If you are transitioning from Skype for Business Online, you need to confirm that a Microsoft Teams license is assigned to the user.</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="6ceeb-107">Установка группы для предоставления концентратора из хранилища Microsoft</span><span class="sxs-lookup"><span data-stu-id="6ceeb-107">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="6ceeb-108">Эти инструкции предназначены для установки групп для сервера-концентратора поверхность из хранилища Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-108">These instructions are for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="6ceeb-109">Запустите хранилища Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="6ceeb-109">Start the Microsoft Store:</span></span><br>
   <span data-ttu-id="6ceeb-110">а.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-110">a.</span></span> <span data-ttu-id="6ceeb-111">Коснитесь кнопки **Пуск** > **все приложения** > **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-111">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="6ceeb-112">б.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-112">b.</span></span> <span data-ttu-id="6ceeb-113">Коснитесь **устройства сервера-концентратора поверхность учетная запись, управление**.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-113">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="6ceeb-114">в.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-114">c.</span></span> <span data-ttu-id="6ceeb-115">В левой части перейдите на вкладку **приложений и компонентов** .</span><span class="sxs-lookup"><span data-stu-id="6ceeb-115">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="6ceeb-116">г.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-116">d.</span></span> <span data-ttu-id="6ceeb-117">В правой части окна нажмите кнопку **Открыть хранилище** .</span><span class="sxs-lookup"><span data-stu-id="6ceeb-117">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="6ceeb-118">Из магазина Microsoft поиск *Групп Майкрософт*.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-118">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="6ceeb-119">Отображается **Группами Майкрософт для сервера-концентратора поверхности** .</span><span class="sxs-lookup"><span data-stu-id="6ceeb-119">The **Microsoft Teams for Surface Hub** will be displayed.</span></span> <span data-ttu-id="6ceeb-120">Нажмите кнопку **получить приложение** для установки.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-120">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="6ceeb-121">После завершения установки перезапустите сервер-концентратор поверхности.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-121">When the installation is complete, restart the Surface Hub.</span></span> 

> [!NOTE]
> <span data-ttu-id="6ceeb-122">Не коснитесь **запуска** в списке магазина страницы.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-122">Do not tap **Launch** from the Store listing page.</span></span>

## <a name="make-teams-the-default-calling-and-meetings-application"></a><span data-ttu-id="6ceeb-123">Создание групп по умолчанию звонков и собраний приложения</span><span class="sxs-lookup"><span data-stu-id="6ceeb-123">Make Teams the default calling and meetings application</span></span>
 
<span data-ttu-id="6ceeb-124">Существует два варианта для настройки политики по умолчанию звонков и собраний приложения.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-124">There are two options for configuring the default calling and meetings application policy:</span></span> 

- <span data-ttu-id="6ceeb-125">**Вариант 1**: настройте с помощью USB-ключ.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-125">**Option 1**: Configure via USB key.</span></span> 
- <span data-ttu-id="6ceeb-126">**Вариант 2**: настройка с помощью MDM, такие как Intune.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-126">**Option 2**: Configure via MDM such as Intune.</span></span>
 
### <a name="option-1-configure-via-usb-key"></a><span data-ttu-id="6ceeb-127">Вариант 1: Настройте с помощью USB-ключ</span><span class="sxs-lookup"><span data-stu-id="6ceeb-127">Option 1: Configure via USB key</span></span> 
 
<span data-ttu-id="6ceeb-128">Пакеты можно найти на этой [странице загрузки](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span><span class="sxs-lookup"><span data-stu-id="6ceeb-128">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="6ceeb-129">Выберите один для пакета, который планируется установить и скопируйте его на USB.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-129">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="6ceeb-130">Правильный .ppkg файл, используемый зависит от приложения политику по умолчанию, которое вы хотите применить следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6ceeb-130">The correct .ppkg file to use depends on the default application policy you'd like to apply as follows:</span></span> 

|<span data-ttu-id="6ceeb-131">Число</span><span class="sxs-lookup"><span data-stu-id="6ceeb-131">Number</span></span>  |<span data-ttu-id="6ceeb-132">Описание</span><span class="sxs-lookup"><span data-stu-id="6ceeb-132">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="6ceeb-133">0</span><span class="sxs-lookup"><span data-stu-id="6ceeb-133">0</span></span>     | <span data-ttu-id="6ceeb-134">Предпочитаемый приложения Скайп на начальном экране, доступные команды собраний</span><span class="sxs-lookup"><span data-stu-id="6ceeb-134">Skype preferred app on the Start Screen, Teams Meetings available</span></span>        |
|<span data-ttu-id="6ceeb-135">1</span><span class="sxs-lookup"><span data-stu-id="6ceeb-135">1</span></span>     | <span data-ttu-id="6ceeb-136">Предпочитаемый приложения группы на начальном экране, доступные Скайп собраний</span><span class="sxs-lookup"><span data-stu-id="6ceeb-136">Teams preferred app on the Start Screen, Skype Meetings available</span></span>        |
|<span data-ttu-id="6ceeb-137">2</span><span class="sxs-lookup"><span data-stu-id="6ceeb-137">2</span></span>     | <span data-ttu-id="6ceeb-138">Команды исключительных приложения на начальном экране (недоступно приложение Скайп)</span><span class="sxs-lookup"><span data-stu-id="6ceeb-138">Teams exclusive app on the Start screen (Skype app not available)</span></span>        |
 
1. <span data-ttu-id="6ceeb-139">Присоедините USB-ключ устройство поверхность сервера-концентратора.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-139">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="6ceeb-140">Откройте **Параметры** приложения на устройстве поверхность сервера-концентратора.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-140">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="6ceeb-141">Откройте **Управление учетными записями устройства контактной сервера-концентратора**.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-141">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="6ceeb-142">Откройте **Управление устройствами**.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-142">Open **Device Management**.</span></span> 
5. <span data-ttu-id="6ceeb-143">Нажмите кнопку **Добавить или удалить подготовки пакета**.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-143">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="6ceeb-144">Нажмите кнопку **добавить пакет**.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-144">Click **Add Package**.</span></span>
7. <span data-ttu-id="6ceeb-145">В раскрывающемся меню выберите параметр **Съемный носитель** .</span><span class="sxs-lookup"><span data-stu-id="6ceeb-145">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="6ceeb-146">Добавьте соответствующие <strong>TeamsRTMMode\*.ppkg</strong> пакет, который ранее был скопирован на ключ USB.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-146">Add the appropriate <strong>TeamsRTMMode\*.ppkg</strong> package that was previously copied to the USB key.</span></span> 
9. <span data-ttu-id="6ceeb-147">Перезагрузите устройство поверхность сервера-концентратора.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-147">Restart the Surface Hub device.</span></span> 
10. <span data-ttu-id="6ceeb-148">После перезагрузки устройства, должна появиться возможность запуска приложения группы на начальном экране и присоединиться к собранию из календаря.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-148">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span> 

### <a name="option-2-configure-via-mdm-such-as-intune"></a><span data-ttu-id="6ceeb-149">Вариант 2: Настройка с помощью MDM, такие как Intune</span><span class="sxs-lookup"><span data-stu-id="6ceeb-149">Option 2: Configure via MDM such as Intune</span></span> 

<span data-ttu-id="6ceeb-150">Используйте следующие для настройки политики по умолчанию звонков и собраний приложения с помощью Intune.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-150">Use the following to configure the default calling and meetings application policy via Intune.</span></span> <span data-ttu-id="6ceeb-151">Также можно найти, [развертывание групп Майкрософт для сервера-концентратора поверхность приложение, использующее Intune](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/).</span><span class="sxs-lookup"><span data-stu-id="6ceeb-151">Also see the blog, [Deploy the Microsoft Teams for Surface Hub app using Intune](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/).</span></span>

|<span data-ttu-id="6ceeb-152">Параметр</span><span class="sxs-lookup"><span data-stu-id="6ceeb-152">Setting</span></span>   |<span data-ttu-id="6ceeb-153">Значение</span><span class="sxs-lookup"><span data-stu-id="6ceeb-153">Value</span></span>    |<span data-ttu-id="6ceeb-154">Описание</span><span class="sxs-lookup"><span data-stu-id="6ceeb-154">Description</span></span>    |
|----------|---------|---------|
|<span data-ttu-id="6ceeb-155">Путь</span><span class="sxs-lookup"><span data-stu-id="6ceeb-155">Path</span></span>      | <span data-ttu-id="6ceeb-156">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span><span class="sxs-lookup"><span data-stu-id="6ceeb-156">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span></span>        |
|<span data-ttu-id="6ceeb-157">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6ceeb-157">Data Type</span></span> | <span data-ttu-id="6ceeb-158">целое число (0-2)</span><span class="sxs-lookup"><span data-stu-id="6ceeb-158">integer (0-2)</span></span>   |<span data-ttu-id="6ceeb-159">0 — Скайп предпочитаемый приложения на начальном экране, доступные команды собраний</span><span class="sxs-lookup"><span data-stu-id="6ceeb-159">0 - Skype preferred app on the Start Screen, Teams Meetings available</span></span><br><span data-ttu-id="6ceeb-160">1 - предпочитаемый приложения группы на начальном экране, доступные Скайп собраний</span><span class="sxs-lookup"><span data-stu-id="6ceeb-160">1 - Teams preferred app on the Start Screen, Skype Meetings available</span></span><br><span data-ttu-id="6ceeb-161">2 - группам исключительных приложения на начальном экране (недоступно приложение Скайп)</span><span class="sxs-lookup"><span data-stu-id="6ceeb-161">2 - Teams exclusive app on the Start screen (Skype app not available)</span></span> |
|<span data-ttu-id="6ceeb-162">Операции</span><span class="sxs-lookup"><span data-stu-id="6ceeb-162">Operations</span></span>| <span data-ttu-id="6ceeb-163">Получение, установка</span><span class="sxs-lookup"><span data-stu-id="6ceeb-163">Get, Set</span></span>        |

|<span data-ttu-id="6ceeb-164">Параметр</span><span class="sxs-lookup"><span data-stu-id="6ceeb-164">Setting</span></span>   |<span data-ttu-id="6ceeb-165">Значение</span><span class="sxs-lookup"><span data-stu-id="6ceeb-165">Value</span></span>    |
|----------|---------|
|<span data-ttu-id="6ceeb-166">Путь</span><span class="sxs-lookup"><span data-stu-id="6ceeb-166">Path</span></span>      | <span data-ttu-id="6ceeb-167">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span><span class="sxs-lookup"><span data-stu-id="6ceeb-167">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span></span>        |
|<span data-ttu-id="6ceeb-168">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6ceeb-168">Data Type</span></span> | <span data-ttu-id="6ceeb-169">Строка — строка набора к группам код пакета приложения как **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! Группы**</span><span class="sxs-lookup"><span data-stu-id="6ceeb-169">string - set string to Teams application package ID as **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams**</span></span> |
|<span data-ttu-id="6ceeb-170">Операции</span><span class="sxs-lookup"><span data-stu-id="6ceeb-170">Operations</span></span>| <span data-ttu-id="6ceeb-171">Получение, установка</span><span class="sxs-lookup"><span data-stu-id="6ceeb-171">Get, Set</span></span>        |

<span data-ttu-id="6ceeb-172">Перезагрузите устройство поверхность сервера-концентратора.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-172">Restart the Surface Hub device.</span></span> <span data-ttu-id="6ceeb-173">После перезагрузки устройства, должна появиться возможность запуска приложения группы на начальном экране и присоединиться к собранию из календаря.</span><span class="sxs-lookup"><span data-stu-id="6ceeb-173">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span>

