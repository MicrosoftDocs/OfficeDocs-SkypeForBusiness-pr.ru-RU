---
title: Управление сетевыми областями
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Сетевой регион * — это сетевые разветвители или кости, используемые в настройке управления допуском звонков, E9-1-1 и мультимедиа.
ms.openlocfilehash: 8d1d60389fe910e2b5c2b8b1c357520aad30db96
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279531"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="a461c-103">Управление сетевыми областями в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a461c-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="a461c-104">*Регионы сетей* — это сетевые разветвители и одинарные кости, используемые в настройке управления допуском звонков, E9-1-1 и мультимедийными пропусками.</span><span class="sxs-lookup"><span data-stu-id="a461c-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="a461c-105">Следующие процедуры служат для просмотра, создания и изменения областей сети.</span><span class="sxs-lookup"><span data-stu-id="a461c-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="a461c-106">Например, если вы уже создали сетевые регионы для одной голосовой связи, вам не нужно создавать новые сетевые регионы; другие дополнительные функции для корпоративной голосовой связи будут использовать те же сетевые регионы.</span><span class="sxs-lookup"><span data-stu-id="a461c-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="a461c-107">Однако вам может потребоваться изменить существующее определение области сети для применения параметров, относящихся к функции.</span><span class="sxs-lookup"><span data-stu-id="a461c-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="a461c-108">Например, если вы создали области сети для службы E9-1-1, для которой не требуется связанный центральный сайт, и затем развернули службу контроля допуска звонков, вам потребуется изменить определения областей сети, чтобы указать центральный сайт.</span><span class="sxs-lookup"><span data-stu-id="a461c-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="a461c-109">В этой статье описаны процедуры для просмотра сведений о сетевом регионе, создания, изменения и удаления регионов сети.</span><span class="sxs-lookup"><span data-stu-id="a461c-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="a461c-110">Просмотр сведений о сетевом регионе</span><span class="sxs-lookup"><span data-stu-id="a461c-110">View network region information</span></span> 


<span data-ttu-id="a461c-111">Сетевой регион соединяет различные части сети в нескольких географических регионах.</span><span class="sxs-lookup"><span data-stu-id="a461c-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="a461c-112">Каждый сетевой регион должен быть связан с центральным сайтом.</span><span class="sxs-lookup"><span data-stu-id="a461c-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="a461c-113">Центральный сайт — это сайт центра обработки данных, на котором запущена служба политики "Управление допуском звонков" (CAC).</span><span class="sxs-lookup"><span data-stu-id="a461c-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="a461c-114">Вы можете использовать панель управления Skype для бизнеса Server для просмотра областей сети.</span><span class="sxs-lookup"><span data-stu-id="a461c-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="a461c-115">Сетевые регионы включают параметры, определяющие, разрешены ли для аудио-и видеоподключений альтернативные пути через Интернет.</span><span class="sxs-lookup"><span data-stu-id="a461c-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="a461c-116">Используйте этот раздел для просмотра существующих областей сети.</span><span class="sxs-lookup"><span data-stu-id="a461c-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="a461c-117">Просмотр сведений о регионе сети с помощью панели управления "Skype для бизнеса Server"</span><span class="sxs-lookup"><span data-stu-id="a461c-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="a461c-118">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a461c-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a461c-119">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a461c-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a461c-120">На панели навигации слева выберите пункт **Настройка сети**, а затем — пункт **регион**.</span><span class="sxs-lookup"><span data-stu-id="a461c-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="a461c-121">На странице **регион** выберите область, которую вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="a461c-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="a461c-122">Вы можете просматривать только один регион за раз.</span><span class="sxs-lookup"><span data-stu-id="a461c-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="a461c-123">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="a461c-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a461c-124">Просмотр сведений о сетевом регионе с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a461c-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="a461c-125">Вы можете просматривать сведения о сетевой области с помощью Windows PowerShell и командлета **Get-кснетворкрегион** .</span><span class="sxs-lookup"><span data-stu-id="a461c-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="a461c-126">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a461c-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="a461c-127">Просмотр сведений о сетевом регионе</span><span class="sxs-lookup"><span data-stu-id="a461c-127">To view network region information</span></span>

  - <span data-ttu-id="a461c-128">Чтобы просмотреть сведения обо всех регионах сети, введите в командной консоли Skype для Business Server указанную ниже команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="a461c-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="a461c-129">Команда возвращает примерно следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="a461c-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="a461c-130">Дополнительные сведения можно найти в разделе справки по командлету [Get-кснетворкрегион](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .</span><span class="sxs-lookup"><span data-stu-id="a461c-130">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="a461c-131">Создание и изменение регионов сети</span><span class="sxs-lookup"><span data-stu-id="a461c-131">Create or modify network regions</span></span> 

<span data-ttu-id="a461c-132">Сетевой регион соединяет различные части сети в нескольких географических регионах.</span><span class="sxs-lookup"><span data-stu-id="a461c-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="a461c-133">Каждый сетевой регион должен быть связан с центральным сайтом.</span><span class="sxs-lookup"><span data-stu-id="a461c-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="a461c-134">Центральный сайт — это сайт центра обработки данных, на котором запущена служба политики "Управление допуском звонков" (CAC).</span><span class="sxs-lookup"><span data-stu-id="a461c-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="a461c-135">Вы можете настроить регионы сети с помощью панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a461c-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="a461c-136">Сетевые регионы включают параметры, определяющие, разрешены ли для аудио-и видеоподключений альтернативные пути через Интернет.</span><span class="sxs-lookup"><span data-stu-id="a461c-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="a461c-137">С помощью панели управления Skype для бизнеса Server вы можете создавать, изменять и удалять сетевые регионы.</span><span class="sxs-lookup"><span data-stu-id="a461c-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="a461c-138">Используйте этот раздел для создания и изменения областей сети.</span><span class="sxs-lookup"><span data-stu-id="a461c-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="a461c-139">Создание сетевого региона</span><span class="sxs-lookup"><span data-stu-id="a461c-139">To create a network region</span></span>

1.  <span data-ttu-id="a461c-140">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a461c-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a461c-141">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a461c-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a461c-142">На панели навигации слева выберите пункт **Настройка сети**, а затем — пункт **регион**.</span><span class="sxs-lookup"><span data-stu-id="a461c-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="a461c-143">На странице **регион** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="a461c-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="a461c-144">На странице **новый регион** введите значение в поле **имя** .</span><span class="sxs-lookup"><span data-stu-id="a461c-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="a461c-145">Это значение должно быть уникальным в рамках развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a461c-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="a461c-146">Из раскрывающегося списка **центральное место** выберите Центральный сайт для этого сетевого региона.</span><span class="sxs-lookup"><span data-stu-id="a461c-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="a461c-147">Флажок **включить звуковой путь** по умолчанию установлен.</span><span class="sxs-lookup"><span data-stu-id="a461c-147">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="a461c-148">Это поле определяет, следует ли перенаправлять голосовые звонки по альтернативному пути, если в основном пути нет необходимой пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="a461c-148">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="a461c-149">Снимите этот флажок, только если вам нужно отключить разгрузку в Интернете.</span><span class="sxs-lookup"><span data-stu-id="a461c-149">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="a461c-150">Если какой-либо из ваших звонков будет звонить через Интернет, этот флажок должен быть установлен, независимо от настройки пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="a461c-150">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="a461c-151">Флажок **включить альтернативный путь** для видеоролика установлен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a461c-151">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="a461c-152">Это поле определяет, следует ли перенаправлять видеозвонки по альтернативному пути, если в основном пути нет необходимой пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="a461c-152">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="a461c-153">Снимите этот флажок, только если вам нужно отключить разгрузку в Интернете.</span><span class="sxs-lookup"><span data-stu-id="a461c-153">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="a461c-154">Если какой-либо из ваших звонков будет звонить через Интернет, этот флажок должен быть установлен, независимо от настройки пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="a461c-154">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="a461c-155">Необязательно Введите значение в поле **Описание** , чтобы получить дополнительные сведения об этой области, которые нельзя выразить только именем.</span><span class="sxs-lookup"><span data-stu-id="a461c-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="a461c-156">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="a461c-156">Click **Commit**.</span></span>

<span data-ttu-id="a461c-157">Таблица " **связанные сайты** " не используется для создания сетевого региона.</span><span class="sxs-lookup"><span data-stu-id="a461c-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="a461c-158">Вы связываете сайт с регионом при создании или изменении сайта.</span><span class="sxs-lookup"><span data-stu-id="a461c-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="a461c-159">Подробности можно найти в разделе [Управление допуском звонков для сайтов](managing-call-admission-control-for-sites.md).</span><span class="sxs-lookup"><span data-stu-id="a461c-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="a461c-160">Изменение сетевого региона</span><span class="sxs-lookup"><span data-stu-id="a461c-160">To modify a network region</span></span>

1.  <span data-ttu-id="a461c-161">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a461c-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a461c-162">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a461c-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a461c-163">На панели навигации слева выберите пункт **Настройка сети**, а затем — пункт **регион**.</span><span class="sxs-lookup"><span data-stu-id="a461c-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="a461c-164">На странице **регион** щелкните область, которую вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="a461c-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="a461c-165">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="a461c-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="a461c-166">На странице **изменить область** вы можете изменить параметры включения и отключения звуковых и видеофайлов, а также изменения их описания (Дополнительные сведения можно найти в разделе "Создание сетевого региона" ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="a461c-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="a461c-167">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="a461c-167">Click **Commit**.</span></span>

<span data-ttu-id="a461c-168">На этой странице невозможно изменить **связанные сайты** .</span><span class="sxs-lookup"><span data-stu-id="a461c-168">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="a461c-169">Список связанных сайтов предоставляется для справки, поэтому вы узнаете, какие сайты будут затронуты при изменении параметров региона.</span><span class="sxs-lookup"><span data-stu-id="a461c-169">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="a461c-170">Удаление существующих областей сети</span><span class="sxs-lookup"><span data-stu-id="a461c-170">Delete existing network regions</span></span> 

<span data-ttu-id="a461c-171">Сетевой регион соединяет различные части сети в нескольких географических регионах.</span><span class="sxs-lookup"><span data-stu-id="a461c-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="a461c-172">Каждый сетевой регион должен быть связан с центральным сайтом.</span><span class="sxs-lookup"><span data-stu-id="a461c-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="a461c-173">Центральный сайт — это сайт центра обработки данных, на котором запущена служба политики "Управление допуском звонков" (CAC).</span><span class="sxs-lookup"><span data-stu-id="a461c-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="a461c-174">Вы можете настроить регионы сети с помощью панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a461c-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="a461c-175">Сетевые регионы включают параметры, определяющие, разрешены ли для аудио-и видеоподключений альтернативные пути через Интернет.</span><span class="sxs-lookup"><span data-stu-id="a461c-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="a461c-176">С помощью панели управления Skype для бизнеса Server вы можете создавать, изменять и удалять сетевые регионы.</span><span class="sxs-lookup"><span data-stu-id="a461c-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="a461c-177">Используйте этот раздел для удаления существующих областей сети.</span><span class="sxs-lookup"><span data-stu-id="a461c-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="a461c-178">Удаление сетевого региона</span><span class="sxs-lookup"><span data-stu-id="a461c-178">To delete a network region</span></span>

1.  <span data-ttu-id="a461c-179">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a461c-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a461c-180">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a461c-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a461c-181">На панели навигации слева выберите пункт **Настройка сети**, а затем — пункт **регион**.</span><span class="sxs-lookup"><span data-stu-id="a461c-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="a461c-182">На странице **регион** выберите область, которую вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="a461c-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="a461c-183">За один раз можно удалить несколько областей.</span><span class="sxs-lookup"><span data-stu-id="a461c-183">You can delete more than one region at a time.</span></span> <span data-ttu-id="a461c-184">Для этого нажмите клавишу CTRL и, удерживая нажатой клавишу CTRL, щелкните несколько областей.</span><span class="sxs-lookup"><span data-stu-id="a461c-184">To do this, press CTRL and select multiple regions while holding down the CTRL key.</span></span> <span data-ttu-id="a461c-185">Кроме того, чтобы выделить все области, в меню **Правка** выберите команду **выделить все** .</span><span class="sxs-lookup"><span data-stu-id="a461c-185">Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="a461c-186">В меню **Правка** выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="a461c-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="a461c-187">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a461c-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="a461c-188">Сетевая область не может быть удалена, если она связана с сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="a461c-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="a461c-189">При попытке удалить область, связанную с сайтом, появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="a461c-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="a461c-190">Чтобы узнать, связана ли область с любыми сайтами, выберите ее, а затем в меню **Правка** выберите команду **Показать подробности** .</span><span class="sxs-lookup"><span data-stu-id="a461c-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="a461c-191">См. также</span><span class="sxs-lookup"><span data-stu-id="a461c-191">See Also</span></span>

[<span data-ttu-id="a461c-192">Управление маршрутами сетевого региона</span><span class="sxs-lookup"><span data-stu-id="a461c-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="a461c-193">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="a461c-193">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="a461c-194">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="a461c-194">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="a461c-195">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="a461c-195">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="a461c-196">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="a461c-196">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
