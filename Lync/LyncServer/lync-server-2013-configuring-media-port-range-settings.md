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
ms.openlocfilehash: 80e835bfcf12495c75612ecee93d87cf3c421651
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a><span data-ttu-id="ae367-102">Настройка параметров диапазона портов мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae367-102">Configuring media port range settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae367-103">_**Тема последнего изменения:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="ae367-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="ae367-104">Параметры диапазона портов мультимедиа могут значительно повлиять на производительность клиента и должны настраиваться.</span><span class="sxs-lookup"><span data-stu-id="ae367-104">Media port range settings can significantly impact client performance and should be configured.</span></span> <span data-ttu-id="ae367-105">Эти параметры можно настроить с помощью командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ae367-105">You can configure these settings by using Lync Server Management Shell.</span></span>

### <a name="media-port-range-settings"></a><span data-ttu-id="ae367-106">Параметры диапазона портов мультимедиа</span><span class="sxs-lookup"><span data-stu-id="ae367-106">Media Port Range Settings</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ae367-107">Параметр</span><span class="sxs-lookup"><span data-stu-id="ae367-107">Setting</span></span></th>
<th><span data-ttu-id="ae367-108">Описание</span><span class="sxs-lookup"><span data-stu-id="ae367-108">Description</span></span></th>
<th><span data-ttu-id="ae367-109">Командлет командной консоли Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="ae367-109">Lync Server Management Shell cmdlet</span></span></th>
<th><span data-ttu-id="ae367-110">Параметры командлета</span><span class="sxs-lookup"><span data-stu-id="ae367-110">Cmdlet parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae367-111">портранже\енаблед</span><span class="sxs-lookup"><span data-stu-id="ae367-111">Portrange\Enabled</span></span></p></td>
<td><p><span data-ttu-id="ae367-112">Указывает, следует ли использовать для мультимедиа и сигналов диапазоны портов, отправленные сервером.</span><span class="sxs-lookup"><span data-stu-id="ae367-112">Specifies whether the port ranges sent by the server should be used by the client for media and signaling.</span></span> <span data-ttu-id="ae367-113">Используется вместе с подзначениями Минмедиапорт и Максмедиапорт.</span><span class="sxs-lookup"><span data-stu-id="ae367-113">Used in conjunction with the subvalues MinMediaPort and MaxMediaPort.</span></span></p></td>
<td><p><span data-ttu-id="ae367-114"><strong>ксконференЦингконфигуратион</strong></span><span class="sxs-lookup"><span data-stu-id="ae367-114"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="ae367-115">клиентмедиапортранжеенаблед</span><span class="sxs-lookup"><span data-stu-id="ae367-115">ClientMediaPortRangeEnabled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae367-116">портранже\минмедиапорт</span><span class="sxs-lookup"><span data-stu-id="ae367-116">Portrange\MinMediaPort</span></span></p></td>
<td><p><span data-ttu-id="ae367-117">Задает начальный номер порта, который будет использоваться для мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="ae367-117">Specifies the starting port number to use for media.</span></span> <span data-ttu-id="ae367-118">Объединяется с Максмедиапорт, чтобы указать диапазон портов.</span><span class="sxs-lookup"><span data-stu-id="ae367-118">Combines with MaxMediaPort to specify the range of ports.</span></span> <span data-ttu-id="ae367-119">Рекомендуемый минимальный диапазон составляет 40 портов.</span><span class="sxs-lookup"><span data-stu-id="ae367-119">The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="ae367-120"><strong>ксконференЦингконфигуратион</strong></span><span class="sxs-lookup"><span data-stu-id="ae367-120"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="ae367-121">Клиентмедиапорт (представляет начальный номер порта, используемый для мультимедиа клиента).</span><span class="sxs-lookup"><span data-stu-id="ae367-121">ClientMediaPort (represents the starting port number to use for client media)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae367-122">портранже\максмедиапорт</span><span class="sxs-lookup"><span data-stu-id="ae367-122">Portrange\MaxMediaPort</span></span></p></td>
<td><p><span data-ttu-id="ae367-123">Указывает самый высокий номер порта, который будет использоваться для мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="ae367-123">Specifies the highest port number to use for media.</span></span> <span data-ttu-id="ae367-124">Объединяется с Минмедиапорт, чтобы указать диапазон портов.</span><span class="sxs-lookup"><span data-stu-id="ae367-124">Combines with MinMediaPort to specify the range of ports.</span></span> <span data-ttu-id="ae367-125">Рекомендуемый минимальный диапазон составляет 40 портов.</span><span class="sxs-lookup"><span data-stu-id="ae367-125">The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="ae367-126"><strong>ксконференЦингконфигуратион</strong></span><span class="sxs-lookup"><span data-stu-id="ae367-126"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="ae367-127">Клиентмедиапортранже (указывает общее количество портов, доступных для клиентского носителя; значение по умолчанию — 40).</span><span class="sxs-lookup"><span data-stu-id="ae367-127">ClientMediaPortRange (indicates the total number of ports available for client media; default is 40)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a><span data-ttu-id="ae367-128">Настройка параметров диапазона портов мультимедиа</span><span class="sxs-lookup"><span data-stu-id="ae367-128">To Configure Media Port Range Settings</span></span>

1.  <span data-ttu-id="ae367-129">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ae367-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ae367-130">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="ae367-130">Run the following cmdlet:</span></span>
    
        Get-CsConferencingConfiguration
    
    <span data-ttu-id="ae367-131">Этот командлет возвращает параметры конфигурации Конференции.</span><span class="sxs-lookup"><span data-stu-id="ae367-131">This cmdlet returns the conferencing configuration settings.</span></span>

3.  <span data-ttu-id="ae367-132">Выполните следующий командлет с параметрами и значениями, которые вы хотите изменить (Дополнительные сведения о параметрах этого командлета можно найти в документации на Lync Server Management Shell).</span><span class="sxs-lookup"><span data-stu-id="ae367-132">Run the following cmdlet with the parameters and values you want to change (for details about the parameters for this cmdlet, see the Lync Server Management Shell documentation):</span></span>
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ae367-133">Вы можете создавать дополнительные наборы параметров настройки конференц-связи для определенных сайтов.</span><span class="sxs-lookup"><span data-stu-id="ae367-133">You can create additional sets of conferencing configuration settings for specific sites.</span></span> <span data-ttu-id="ae367-134">Используйте командлет <STRONG>New-ксконференЦингконфигуратион</STRONG> с удостоверением сайта.</span><span class="sxs-lookup"><span data-stu-id="ae367-134">Use the <STRONG>New- CsConferencingConfiguration</STRONG> cmdlet with a site identity.</span></span> <span data-ttu-id="ae367-135">При создании новых параметров конфигурации конференций для сайтов параметры сайта имеют приоритет над глобальными параметрами.</span><span class="sxs-lookup"><span data-stu-id="ae367-135">When you create new conferencing configuration settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="ae367-136">Подробные сведения можно найти в руководстве по среде Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ae367-136">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

