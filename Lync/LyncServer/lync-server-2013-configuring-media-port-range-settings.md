---
title: 'Lync Server 2013: Настройка параметров диапазона портов мультимедиа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cfde603ace9036ba547ffb0a7ee80c1963ae6cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a><span data-ttu-id="b03f0-102">Настройка параметров диапазона портов мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b03f0-102">Configuring media port range settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b03f0-103">_**Последнее изменение темы:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="b03f0-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="b03f0-104">Параметры диапазона портов медиаданных могут значительно влиять на производительность клиента и должны быть настроены.</span><span class="sxs-lookup"><span data-stu-id="b03f0-104">Media port range settings can significantly impact client performance and should be configured.</span></span> <span data-ttu-id="b03f0-105">Эти параметры можно настроить с помощью консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b03f0-105">You can configure these settings by using Lync Server Management Shell.</span></span>

### <a name="media-port-range-settings"></a><span data-ttu-id="b03f0-106">Параметры диапазона портов медиаданных</span><span class="sxs-lookup"><span data-stu-id="b03f0-106">Media Port Range Settings</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b03f0-107">Параметр</span><span class="sxs-lookup"><span data-stu-id="b03f0-107">Setting</span></span></th>
<th><span data-ttu-id="b03f0-108">Описание</span><span class="sxs-lookup"><span data-stu-id="b03f0-108">Description</span></span></th>
<th><span data-ttu-id="b03f0-109">Командлет командной консоли Lync Server</span><span class="sxs-lookup"><span data-stu-id="b03f0-109">Lync Server Management Shell cmdlet</span></span></th>
<th><span data-ttu-id="b03f0-110">Параметры командлета</span><span class="sxs-lookup"><span data-stu-id="b03f0-110">Cmdlet parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b03f0-111">портранже\енаблед</span><span class="sxs-lookup"><span data-stu-id="b03f0-111">Portrange\Enabled</span></span></p></td>
<td><p><span data-ttu-id="b03f0-p102">Определяет, должен ли клиент использовать диапазоны портов, отправленные сервером, для обработки медиаданных и сигнализации. Используется в сочетании со значениями MinMediaPort и MaxMediaPort.</span><span class="sxs-lookup"><span data-stu-id="b03f0-p102">Specifies whether the port ranges sent by the server should be used by the client for media and signaling. Used in conjunction with the subvalues MinMediaPort and MaxMediaPort.</span></span></p></td>
<td><p><span data-ttu-id="b03f0-114"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="b03f0-114"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="b03f0-115">Параметры clientmediaportrangeenabled</span><span class="sxs-lookup"><span data-stu-id="b03f0-115">ClientMediaPortRangeEnabled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b03f0-116">портранже\минмедиапорт</span><span class="sxs-lookup"><span data-stu-id="b03f0-116">Portrange\MinMediaPort</span></span></p></td>
<td><p><span data-ttu-id="b03f0-p103">Определяет начальный номер порта медиаданных. Вместе с параметром MaxMediaPort позволяет задать диапазон портов. Рекомендуемый минимальный диапазон составляет 40 портов.</span><span class="sxs-lookup"><span data-stu-id="b03f0-p103">Specifies the starting port number to use for media. Combines with MaxMediaPort to specify the range of ports. The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="b03f0-120"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="b03f0-120"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="b03f0-121">ClientMediaPort (представляет собой начальный номер порта медиаданных клиента)</span><span class="sxs-lookup"><span data-stu-id="b03f0-121">ClientMediaPort (represents the starting port number to use for client media)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b03f0-122">портранже\максмедиапорт</span><span class="sxs-lookup"><span data-stu-id="b03f0-122">Portrange\MaxMediaPort</span></span></p></td>
<td><p><span data-ttu-id="b03f0-p104">Определяет максимальный номер порта медиаданных. Вместе с параметром MinMediaPort позволяет задать диапазон портов. Рекомендуемый минимальный диапазон составляет 40 портов.</span><span class="sxs-lookup"><span data-stu-id="b03f0-p104">Specifies the highest port number to use for media. Combines with MinMediaPort to specify the range of ports. The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="b03f0-126"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="b03f0-126"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="b03f0-127">ClientMediaPortRange (определяет общее число портов, доступных для медиаданных клиента; по умолчанию: 40)</span><span class="sxs-lookup"><span data-stu-id="b03f0-127">ClientMediaPortRange (indicates the total number of ports available for client media; default is 40)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a><span data-ttu-id="b03f0-128">Порядок настройки параметров диапазона портов медиаданных</span><span class="sxs-lookup"><span data-stu-id="b03f0-128">To Configure Media Port Range Settings</span></span>

1.  <span data-ttu-id="b03f0-129">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b03f0-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b03f0-130">Выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="b03f0-130">Run the following cmdlet:</span></span>
    
        Get-CsConferencingConfiguration
    
    <span data-ttu-id="b03f0-131">Этот командлет возвращает параметры конфигурации конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="b03f0-131">This cmdlet returns the conferencing configuration settings.</span></span>

3.  <span data-ttu-id="b03f0-132">Выполните следующий командлет с параметрами и значениями, которые требуется изменить (Дополнительные сведения о параметрах этого командлета см. в документации по командной консоли Lync Server).</span><span class="sxs-lookup"><span data-stu-id="b03f0-132">Run the following cmdlet with the parameters and values you want to change (for details about the parameters for this cmdlet, see the Lync Server Management Shell documentation):</span></span>
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b03f0-133">Можно создавать дополнительные наборы параметров конфигурации конференц-связи для отдельных сайтов.</span><span class="sxs-lookup"><span data-stu-id="b03f0-133">You can create additional sets of conferencing configuration settings for specific sites.</span></span> <span data-ttu-id="b03f0-134">Используйте командлет <STRONG>New- CsConferencingConfiguration</STRONG> с указанием идентификатора сайта.</span><span class="sxs-lookup"><span data-stu-id="b03f0-134">Use the <STRONG>New- CsConferencingConfiguration</STRONG> cmdlet with a site identity.</span></span> <span data-ttu-id="b03f0-135">При создании новых параметров конфигурации конференц-связи для сайтов эти параметры сайтов имеют приоритет перед глобальными параметрами.</span><span class="sxs-lookup"><span data-stu-id="b03f0-135">When you create new conferencing configuration settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="b03f0-136">Дополнительные сведения см. в документации Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b03f0-136">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

