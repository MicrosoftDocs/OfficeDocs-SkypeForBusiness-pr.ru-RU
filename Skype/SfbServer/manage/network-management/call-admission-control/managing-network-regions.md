---
title: Управление областями сети
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Сетевой регион * являются сетевых концентраторов и магистралей, используемые в конфигурации обход элемента управления, E9-1-1 и мультимедиа допуска звонков.
ms.openlocfilehash: c7559c8fa09d0f0d7fac4fa5067d2df91c52defe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913372"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="4cb6d-103">Управление сетевыми областями в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4cb6d-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="4cb6d-104">*Области сети* являются сетевых концентраторов и магистралей, используемые в конфигурации обход элемента управления, E9-1-1 и мультимедиа допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="4cb6d-105">Используйте следующие процедуры для просмотра, создания или изменения областей сети.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="4cb6d-106">Например если вы уже создали областей сети для одного компонента голосовой связи, не нужно создать новые области сети; другие расширенные функции корпоративной голосовой связи будет использовать те же области сети.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="4cb6d-107">Однако вам может потребоваться изменить существующее определение области сети для применения параметров, относящихся к функции.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="4cb6d-108">Например, если вы создали области сети для службы E9-1-1, для которой не требуется связанный центральный сайт, и затем развернули службу контроля допуска звонков, вам потребуется изменить определения областей сети, чтобы указать центральный сайт.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="4cb6d-109">Используйте процедуры, описанные в этой статье для просмотра сведений о сетевом регионе или создание, изменение и удаление областей сети.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="4cb6d-110">Просмотр сведений о сетевом регионе</span><span class="sxs-lookup"><span data-stu-id="4cb6d-110">View network region information</span></span> 


<span data-ttu-id="4cb6d-111">Область сети соединения различные части сети через несколько географических областей.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="4cb6d-112">Каждой области сети должен быть связан с центральным узлом.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="4cb6d-113">Центральный узел является сайт центра данных, на котором запущена служба политики пропускной способности контроля допуска допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="4cb6d-114">Скайп для панели управления Business Server можно использовать для просмотра областей сети.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="4cb6d-115">Области сети включают параметры, определяющие, разрешены ли альтернативные маршруты через Интернет для подключения к аудио- и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="4cb6d-116">Используйте этот раздел для просмотра существующих областей сети.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="4cb6d-117">Чтобы просмотреть сведения об области сети с Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="4cb6d-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="4cb6d-118">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4cb6d-119">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4cb6d-120">В левой панели навигации щелкните **Конфигурация сети**и затем выберите **Регион**.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="4cb6d-121">На странице **область** щелкните область, которую необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="4cb6d-122">Можно просматривать только один регион.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="4cb6d-123">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4cb6d-124">Просмотр сведений о сетевом регионе с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4cb6d-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="4cb6d-125">Сведений о сетевом регионе можно просмотреть с помощью Windows PowerShell и командлета **Get-CsNetworkRegion** .</span><span class="sxs-lookup"><span data-stu-id="4cb6d-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="4cb6d-126">Можно выполнить этот командлет из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="4cb6d-127">Для просмотра сведений о сетевом регионе</span><span class="sxs-lookup"><span data-stu-id="4cb6d-127">To view network region information</span></span>

  - <span data-ttu-id="4cb6d-128">Чтобы просмотреть сведения обо всех сетевых регионах, введите следующую команду в Скайп для консоли Business Server и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="4cb6d-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="4cb6d-129">Команда возвращает примерно следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="4cb6d-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="4cb6d-130">Для получения дополнительных сведений см раздел справки для командлета [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .</span><span class="sxs-lookup"><span data-stu-id="4cb6d-130">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="4cb6d-131">Создание или изменение областей сети</span><span class="sxs-lookup"><span data-stu-id="4cb6d-131">Create or modify network regions</span></span> 

<span data-ttu-id="4cb6d-132">Область сети соединения различные части сети через несколько географических областей.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="4cb6d-133">Каждой области сети должен быть связан с центральным узлом.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="4cb6d-134">Центральный узел является сайт центра данных, на котором запущена служба политики пропускной способности контроля допуска допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="4cb6d-135">Настройка сетевых областей можно использовать Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="4cb6d-136">Области сети включают параметры, определяющие, разрешены ли альтернативные маршруты через Интернет для подключения к аудио- и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="4cb6d-137">Из Скайп для панели управления Business Server создание, изменение или удаление области сети.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="4cb6d-138">Используйте этот раздел для создания и изменения областей сети.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="4cb6d-139">Создание области сети</span><span class="sxs-lookup"><span data-stu-id="4cb6d-139">To create a network region</span></span>

1.  <span data-ttu-id="4cb6d-140">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4cb6d-141">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4cb6d-142">В левой панели навигации щелкните **Конфигурация сети**и затем выберите **Регион**.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="4cb6d-143">На странице **область** щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="4cb6d-144">На странице " **Создание области** " введите значение в поле **имя** .</span><span class="sxs-lookup"><span data-stu-id="4cb6d-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="4cb6d-145">Это значение должно быть уникальным в рамках вашей Скайп для развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="4cb6d-146">В раскрывающемся списке **центральный сайт** выберите центральный сайт для этой области сети.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="4cb6d-147">По умолчанию установлен флажок **Включение звука альтернативный путь** .</span><span class="sxs-lookup"><span data-stu-id="4cb6d-147">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="4cb6d-148">В этом поле определяет ли голосовые вызовы будут перенаправляться по альтернативному пути, если не пропускной способности основного пути.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-148">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="4cb6d-149">Снимите этот флажок только в том случае, если требуется отключить разгрузки в Интернет.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-149">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="4cb6d-150">Если какие-либо из ваших вызовов будет звонком через Интернет, этот флажок, должен быть установлен, вне зависимости от параметров пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-150">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="4cb6d-151">По умолчанию установлен флажок **Включить видео альтернативный путь** .</span><span class="sxs-lookup"><span data-stu-id="4cb6d-151">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="4cb6d-152">В этом поле определяет, будет ли видео звонки будут перенаправляться по альтернативному пути, если не пропускной способности основного пути.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-152">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="4cb6d-153">Снимите этот флажок только в том случае, если требуется отключить разгрузки в Интернет.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-153">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="4cb6d-154">Если какие-либо из ваших вызовов будет звонком через Интернет, этот флажок, должен быть установлен, вне зависимости от параметров пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-154">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="4cb6d-155">(Необязательно) Введите значение в поле **Описание** введите дополнительные сведения об области, которые не могут быть выражены одним именем.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="4cb6d-156">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-156">Click **Commit**.</span></span>

<span data-ttu-id="4cb6d-157">В таблице **связанные сайты** не используется для создания области сети.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="4cb6d-158">Сайт связать с областью, при создании или изменении сайта.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="4cb6d-159">Дополнительные сведения см [Управление контроля допуска звонков для сайтов](managing-call-admission-control-for-sites.md).</span><span class="sxs-lookup"><span data-stu-id="4cb6d-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="4cb6d-160">Изменение области сети</span><span class="sxs-lookup"><span data-stu-id="4cb6d-160">To modify a network region</span></span>

1.  <span data-ttu-id="4cb6d-161">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4cb6d-162">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4cb6d-163">В левой панели навигации щелкните **Конфигурация сети**и затем выберите **Регион**.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="4cb6d-164">На странице **область** щелкните область, которую требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="4cb6d-165">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="4cb6d-166">На странице **Изменить область** можно изменить параметры для Включение и отключение звука и видео альтернативных путей и изменить описание (для получения дополнительных сведений, см раздел «Создание области сети» ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="4cb6d-167">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-167">Click **Commit**.</span></span>

<span data-ttu-id="4cb6d-168">**Связанные сайты** на этой странице изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-168">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="4cb6d-169">Список связанных сайтов предоставляется для ссылки, чтобы знать о том, какие сайты будут затронуты при изменении параметров области.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-169">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="4cb6d-170">Удаление существующих областей сети</span><span class="sxs-lookup"><span data-stu-id="4cb6d-170">Delete existing network regions</span></span> 

<span data-ttu-id="4cb6d-171">Область сети соединения различные части сети через несколько географических областей.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="4cb6d-172">Каждой области сети должен быть связан с центральным узлом.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="4cb6d-173">Центральный узел является сайт центра данных, на котором запущена служба политики пропускной способности контроля допуска допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="4cb6d-174">Настройка сетевых областей можно использовать Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="4cb6d-175">Области сети включают параметры, определяющие, разрешены ли альтернативные маршруты через Интернет для подключения к аудио- и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="4cb6d-176">Из Скайп для панели управления Business Server создание, изменение или удаление области сети.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="4cb6d-177">Используйте этот раздел для удаления существующих областей сети.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="4cb6d-178">Чтобы удалить область сети</span><span class="sxs-lookup"><span data-stu-id="4cb6d-178">To delete a network region</span></span>

1.  <span data-ttu-id="4cb6d-179">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4cb6d-180">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4cb6d-181">В левой панели навигации щелкните **Конфигурация сети**и затем выберите **Регион**.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="4cb6d-182">На странице **область** щелкните область, которую вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="4cb6d-183">Одновременно можно удалить более одного региона.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-183">You can delete more than one region at a time.</span></span> <span data-ttu-id="4cb6d-184">Для этого нажмите клавишу CTRL и выберите несколько областей, удерживая нажатой клавишу CTRL.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-184">To do this, press CTRL and select multiple regions while holding down the CTRL key.</span></span> <span data-ttu-id="4cb6d-185">Или, чтобы выбрать все области, нажмите кнопку **Выбрать все** в меню **Правка** .</span><span class="sxs-lookup"><span data-stu-id="4cb6d-185">Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="4cb6d-186">В меню **Правка** выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="4cb6d-187">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="4cb6d-188">Область сети не может быть удалена, если она связана с сетевым узлом.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="4cb6d-189">Если попытаться удалить области, связанные с сайтом, вы получите сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="4cb6d-190">Чтобы просмотреть, если область связана с веб-сайты, выберите область и нажмите кнопку **Показать подробности** в меню **Правка** .</span><span class="sxs-lookup"><span data-stu-id="4cb6d-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="4cb6d-191">См. также</span><span class="sxs-lookup"><span data-stu-id="4cb6d-191">See Also</span></span>

[<span data-ttu-id="4cb6d-192">Управление маршрутов между сетевыми областями</span><span class="sxs-lookup"><span data-stu-id="4cb6d-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="4cb6d-193">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="4cb6d-193">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="4cb6d-194">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="4cb6d-194">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="4cb6d-195">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="4cb6d-195">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="4cb6d-196">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="4cb6d-196">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
