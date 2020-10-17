---
title: Настройка фильтрации передачи файлов и URL-адресов для обмена мгновенными сообщениями (IM)
description: Настройка передачи файлов и фильтрации URL-адресов для обмена мгновенными сообщениями (IM).
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92f11c3f3bb924c1d92361c2635bfb37e1f03175
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548355"
---
# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a><span data-ttu-id="56578-103">Настройка передачи файлов и фильтрации URL-адресов для обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56578-103">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56578-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="56578-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="56578-105">Средство интеллектуального фильтра обмена мгновенными сообщениями помогает защитить развертывание Lync Server 2013 от распространения наиболее распространенных форм вирусов с минимальным снижением качества взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="56578-105">The Intelligent IM Filter tool helps protect your Lync Server 2013 deployment against the spread of the most common forms of viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="56578-106">Используйте Intelligent IM Filter, чтобы настроить фильтры для блокировки потенциально вредоносных мгновенных сообщений от неизвестных конечных точек за пределами корпоративного брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="56578-106">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="56578-107">Фильтры настраиваются путем задания критерия блокировки, например, можно блокировать сообщения содержащие гиперссылки с определенными префиксами и файлами с определенными расширениями.</span><span class="sxs-lookup"><span data-stu-id="56578-107">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks with specific prefixes and files with specific extensions.</span></span>

<span data-ttu-id="56578-108">Фильтр Intelligent IM предоставляет следующее:</span><span class="sxs-lookup"><span data-stu-id="56578-108">Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="56578-109">Улучшенную фильтрацию URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="56578-109">Enhanced URL filtering.</span></span>

  - <span data-ttu-id="56578-110">Улучшенную фильтрацию при передаче файлов.</span><span class="sxs-lookup"><span data-stu-id="56578-110">Enhanced file transfer filtering.</span></span>

<span data-ttu-id="56578-111">Настройка фильтра Intelligent IM:</span><span class="sxs-lookup"><span data-stu-id="56578-111">Configuring Intelligent IM Filter includes the following:</span></span>

  - <span data-ttu-id="56578-112">Настройка URL-фильтра.</span><span class="sxs-lookup"><span data-stu-id="56578-112">Configuring URL filtering.</span></span>

  - <span data-ttu-id="56578-113">Настройка фильтра передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="56578-113">Configuring file transfer filtering.</span></span>

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a><span data-ttu-id="56578-114">Как параметры фильтрации применяются к мгновенным сообщениям</span><span class="sxs-lookup"><span data-stu-id="56578-114">How Filtering Options Are Applied to Instant Messages</span></span>

<span data-ttu-id="56578-115">Перед развертыванием средства фильтрации сообщений Intelligent IM необходимо знать, как применяются параметры фильтрации, когда сообщения маршрутизируются с одного сервера Lync Server 2013 на другой.</span><span class="sxs-lookup"><span data-stu-id="56578-115">Before you deploy the Intelligent IM Message Filter tool, you need to understand how filtering options are applied as messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="56578-116">Параметры фильтрации применяются последовательно, независимо от расположения серверов, будь то пределы одной организации или обмен данными между несколькими организациями.</span><span class="sxs-lookup"><span data-stu-id="56578-116">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="56578-117">Данная последовательность отражается на вставку в сообщения специализированных уведомлений и предупреждений.</span><span class="sxs-lookup"><span data-stu-id="56578-117">This consistency applies to the way that the customized notice and warning texts are inserted into messages and sent across servers.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="56578-118">Фильтр мгновенных сообщений увеличивает нагрузку на ЦП при обработке URL-адресов в сообщении.</span><span class="sxs-lookup"><span data-stu-id="56578-118">The instant message filter increases the amount of CPU resources required to process URLs in a message.</span></span> <span data-ttu-id="56578-119">Этот рост требований ЦП также влияет на производительность Lync Server.</span><span class="sxs-lookup"><span data-stu-id="56578-119">This increase in CPU demand also affects the performance of Lync Server.</span></span>



</div>

<span data-ttu-id="56578-120">С помощью страницы **фильтра URL-адресов** в группе " **IM and Presence** " в панели управления Lync Server вы можете заблокировать некоторые или все гиперссылки или настроить предупреждение.</span><span class="sxs-lookup"><span data-stu-id="56578-120">By using the **URL Filter** page in the **IM and Presence** group in Lync Server Control Panel, you can block some or all hyperlinks or configure a warning.</span></span> <span data-ttu-id="56578-121">Предупреждение вставляется в начало мгновенного сообщения, содержащего гиперссылку, если для настройки **Префикс гиперссылки** выбрать параметр **Отправлять предупреждающее  сообщение**.</span><span class="sxs-lookup"><span data-stu-id="56578-121">The warning is inserted at the beginning of an instant message that contains a hyperlink when you choose the **Hyperlink prefix** option **Send warning message**.</span></span>

<span data-ttu-id="56578-122">При передаче сообщения от одного сервера к другому, действуют следующие общие правила:</span><span class="sxs-lookup"><span data-stu-id="56578-122">When an instant message travels from one server to another, the following general guidelines apply:</span></span>

  - <span data-ttu-id="56578-p105">Если сервер блокирует сообщение (из-за установки флага **Блокировать URL-адреса с расширениями файлов** на странице **URL-фильтр** или из-за установки для опции **Префикс гиперссылки** параметра **Блокировать гиперссылки**), клиенту возвращается сообщение об ошибке. Последующие сервера не получают данное мгновенное сообщение.</span><span class="sxs-lookup"><span data-stu-id="56578-p105">If a server blocks an instant message (because you selected the **Block URLs with file extension** check box on the **URL Filter** page or because you chose the **Hyperlink prefix** option **Block hyperlinks**), an error message is returned to the client. Subsequent servers do not receive this instant message.</span></span>

  - <span data-ttu-id="56578-p106">Если сервер (Server1) добавляет предупреждение в мгновенное сообщение с активной гиперссылкой, то последующий сервер (Server2), получивший данное сообщение все еще может выполнить другое действие на основе присутствующей гиперссылки и заблокировать мгновенное сообщение или добавить свое предупреждение. Если Server2 настроен так, что добавляется предупреждение для данного типа URL-адреса, ранее добавленное Server1 предупреждение убирается и в начало сообщения добавляется предупреждение, заданное для Server2.</span><span class="sxs-lookup"><span data-stu-id="56578-p106">If a server (Server1) adds a warning to an instant message that contains an active hyperlink, a subsequent server (Server2) that receives this instant message can still take a different action based on this active hyperlink present in the instant message and block the instant message or add a warning. If Server2 is configured only to add a warning for this URL, the earlier warning added by Server1 is removed, and the warning configured on Server2 is added to the beginning of the instant message.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="56578-127">Если вы используете Lync Server 2013 в смешанной среде, то для использования интеллектуального фильтра мгновенных сообщений необходимо использовать сервер Live Communications Server 2005 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="56578-127">If you are running Lync Server 2013 in a mixed environment, Live Communications Server 2005 with SP1 is the minimum version required to use the Intelligent IM Filter application.</span></span> <span data-ttu-id="56578-128">Intelligent IM Filter не поддерживается в Live Communications Server 2005 без пакета SP1.</span><span class="sxs-lookup"><span data-stu-id="56578-128">The Intelligent IM Filter is not supported on Live Communications Server 2005 without SP1.</span></span>



</div>

<div>

## <a name="url-filtering"></a><span data-ttu-id="56578-129">Фильтрация URL-адресов</span><span class="sxs-lookup"><span data-stu-id="56578-129">URL Filtering</span></span>

<span data-ttu-id="56578-p108">URL-адреса фильтруются по префиксам гиперссылок. Ниже приведены примеры подобных префиксов:</span><span class="sxs-lookup"><span data-stu-id="56578-p108">URLs are filtered according to their hyperlink prefix. The following examples are valid prefixes:</span></span>

  - <span data-ttu-id="56578-132">www \* .</span><span class="sxs-lookup"><span data-stu-id="56578-132">www\*.</span></span>

  - <span data-ttu-id="56578-133">сервере.</span><span class="sxs-lookup"><span data-stu-id="56578-133">ftp.</span></span>

  - <span data-ttu-id="56578-134">http</span><span class="sxs-lookup"><span data-stu-id="56578-134">http:</span></span>

<span data-ttu-id="56578-p109">Если не задать фильтр URL-адресов, то все адреса в мгновенных сообщениях проходят через сервер без изменений. Если фильтр задан, то адреса в мгновенных сообщения фильтруются согласно параметрам, заданным в диалоговом окне **Изменение URL-фильтра** и **Новый URL-фильтр**.</span><span class="sxs-lookup"><span data-stu-id="56578-p109">If you do not configure the instant message filter to perform any URL filtering, all URLs contained in instant messages are passed unmodified through the server. If you configure the instant message filter to perform URL filtering, URLs in instant messages are filtered according to the options that you select in the **Edit URL Filter** or **New URL Filter** dialog box.</span></span>

  - <span data-ttu-id="56578-137">**Включение фильтра**     URL-адресов Этот параметр включает фильтрацию URL-адресов для глобального развертывания или для выбранного сайта.</span><span class="sxs-lookup"><span data-stu-id="56578-137">**Enable URL filter**   This option enables URL filtering for the global deployment or for the site that you select.</span></span>

  - <span data-ttu-id="56578-138">**Блокировка URL-адресов с расширением файла**     Фильтр мгновенных сообщений блокирует любой активный URL-адрес в интрасети или Интернете, который содержит файл с расширением, указанным в разделе **расширения типов файлов, которые блокируются** в диалоговом окне **Изменение фильтра файлов** .</span><span class="sxs-lookup"><span data-stu-id="56578-138">**Block URLs with file extension**   The instant message filter blocks any active intranet or Internet URL that contains a file with an extension listed under **File type extensions to block** in the **Edit File Filter** dialog box.</span></span> <span data-ttu-id="56578-139">Если URL-адрес заблокирован, отправителю отображается сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="56578-139">When a URL is blocked, an error message is displayed to the sender.</span></span> <span data-ttu-id="56578-140">Если выбран этот параметр, этот параметр имеет приоритет над всеми другими параметрами фильтрации для всех расширений файлов, определенных в разделе **расширения типов файлов для блокировки**.</span><span class="sxs-lookup"><span data-stu-id="56578-140">When selected, this option takes precedence over all other filtering options for any file extensions defined under **File type extensions to block**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="56578-p111">Фильтрация расширений проводится по стандартным названиям файлов. Фильтр может не работать с расширениями файлов, внедренных в другие имена.</span><span class="sxs-lookup"><span data-stu-id="56578-p111">Filtering of file extensions is limited to standard file names. Filtering may not work with file extensions embedded in other names.</span></span>

    
    </div>

<span data-ttu-id="56578-143">Чтобы настроить порядок обработки гиперссылок в обмене мгновенными сообщениями, выберите один из следующих параметров в настройке **Префикс гиперссылки**:</span><span class="sxs-lookup"><span data-stu-id="56578-143">To configure how hyperlinks are handled in instant message conversations, select one of the following options under **Hyperlink prefix**:</span></span>

  - <span data-ttu-id="56578-144">Не **Фильтровать**     URL-адреса в сообщениях отправляются через сервер.</span><span class="sxs-lookup"><span data-stu-id="56578-144">**Do not filter**   URLs in messages are sent through the server.</span></span> <span data-ttu-id="56578-145">Если выбрать данный вариант, появится окно **Разрешить сообщение**.</span><span class="sxs-lookup"><span data-stu-id="56578-145">When you choose this option, the **Allow message** box appears.</span></span> <span data-ttu-id="56578-146">В окне **Разрешить сообщение** задайте уведомление, которое нужно вставлять в начало каждого сообщения с гиперссылкой.</span><span class="sxs-lookup"><span data-stu-id="56578-146">In the **Allow message** box, specify the notice that you want to insert at the beginning of each instant message containing hyperlinks.</span></span> <span data-ttu-id="56578-147">Данное уведомление не может содержать более 65535 символов.</span><span class="sxs-lookup"><span data-stu-id="56578-147">This notice can consist of no more than 65535 characters.</span></span>

  - <span data-ttu-id="56578-148">**Блокировать гиперссылки**     Доставка мгновенных сообщений, содержащих активные гиперссылки, блокируется сервером Lync Server, а отправителю отображается сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="56578-148">**Block hyperlinks**   Delivery of instant messages containing active hyperlinks is blocked by Lync Server, and an error message is displayed to the sender.</span></span>

  - <span data-ttu-id="56578-149">**Отправка предупреждающего сообщения**     Lync Server разрешает активные гиперссылки в мгновенных сообщениях, но включает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="56578-149">**Send warning message**   Lync Server permits active hyperlinks in instant messages, but it includes a warning.</span></span> <span data-ttu-id="56578-150">Если выбрать данный вариант, то откроется окно **Предупреждение**.</span><span class="sxs-lookup"><span data-stu-id="56578-150">When you choose this option, the **Warning message** box appears.</span></span> <span data-ttu-id="56578-151">В окне **Предупреждение** необходимо ввести предупреждение, которое будет добавляться к мгновенным сообщениям с допустимыми гиперссылками.</span><span class="sxs-lookup"><span data-stu-id="56578-151">In the **Warning message** box, you must type the warning that you want to include with instant messages containing valid hyperlinks.</span></span> <span data-ttu-id="56578-152">Например, это предупреждение может сообщать о потенциальной опасности открытия неизвестной ссылки, или напоминать о соответствующих требованиях и правилах вашей организации.</span><span class="sxs-lookup"><span data-stu-id="56578-152">For example, this warning might state the potential dangers of clicking an unknown link, or it might refer to your organization’s relevant policies and requirements.</span></span> <span data-ttu-id="56578-153">Данное предупреждение не может содержать более 65535 символов.</span><span class="sxs-lookup"><span data-stu-id="56578-153">The warning can be no more than 65535 characters.</span></span>

<span data-ttu-id="56578-154">Если выбрать параметр **Блокировать гиперссылки** или **Отправлять предупреждение**, то становятся доступны следующие опции:</span><span class="sxs-lookup"><span data-stu-id="56578-154">If you select **Block hyperlinks** or **Send warning message**, the following options are available:</span></span>

  - <span data-ttu-id="56578-155">**Исключение гиперссылок**     локальной интрасети Фильтр мгновенных сообщений блокирует только URL-адреса в Интернете.</span><span class="sxs-lookup"><span data-stu-id="56578-155">**Exclude local intranet hyperlinks**   The instant message filter blocks only Internet URLs.</span></span> <span data-ttu-id="56578-156">URL-адреса для расположений в интрасети передаются без изменений через сервер.</span><span class="sxs-lookup"><span data-stu-id="56578-156">URLs for locations within your intranet are passed unmodified through the server.</span></span> <span data-ttu-id="56578-157">Тем не менее, URL-адреса интрасети, зависящие от отдельных серверов, на которых работает Lync Server, зависят от того, какие типы локальных веб-сайтов считаются частью зоны интрасети.</span><span class="sxs-lookup"><span data-stu-id="56578-157">However, the intranet URLs that individual servers running Lync Server pass depend on which types of local websites are considered part of their intranet zone.</span></span> <span data-ttu-id="56578-158">Чтобы проверить параметры зоны интрасети сервера, ознакомьтесь со статьей "Настройка параметров интрасети в Internet Explorer", описанной в статье [Изменение фильтра URL-адресов по умолчанию в Lync server 2013](lync-server-2013-modify-the-default-url-filter.md).</span><span class="sxs-lookup"><span data-stu-id="56578-158">To check a server’s intranet zone settings, see the “To configure your intranet settings in Internet Explorer” procedure in [Modify the default URL filter in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md).</span></span>

  - <span data-ttu-id="56578-159">**Фильтрация префиксов гиперссылок**     Чтобы выбрать нужные префиксы, нажмите кнопку **выбрать**, а затем в списке **выбрать префикс гиперссылки**добавьте префиксы в список префиксы **гиперссылок** .</span><span class="sxs-lookup"><span data-stu-id="56578-159">**Filter these hyperlink prefixes**   To choose which prefixes you want to block, click **Select**, and then, in **Select Hyperlink Prefix**, add the prefixes to the **Hyperlink prefixes** list.</span></span>
    
    <span data-ttu-id="56578-160">Все префиксы за исключением **href** должны завершаться точкой или двоеточием, или звездочкой с последующей точки.</span><span class="sxs-lookup"><span data-stu-id="56578-160">All prefixes except **href** must end with a period or a colon, or an asterisk followed by a period.</span></span> <span data-ttu-id="56578-161">Допустимые префиксы могут содержать любой символ из набора допустимых URL-символов, за исключением звездочки ( \* ).</span><span class="sxs-lookup"><span data-stu-id="56578-161">Valid prefixes can contain any characters in the set of valid URL characters except the asterisk (\*).</span></span> <span data-ttu-id="56578-162">Набор допустимых символов URL-адреса: \# \* +/0123456789 = @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^ \_ \` абкдефгхижклмнопкрстуввксиз | ~</span><span class="sxs-lookup"><span data-stu-id="56578-162">The set of valid URL characters is: \#\*+/0123456789=@ABCDEFGHIJKLMNOPQRSTUVWXYZ^\_\` abcdefghijklmnopqrstuvwxyz|~</span></span>

</div>

<div>

## <a name="file-transfer-filtering"></a><span data-ttu-id="56578-163">Фильтрации передачи файлов</span><span class="sxs-lookup"><span data-stu-id="56578-163">File Transfer Filtering</span></span>

<span data-ttu-id="56578-p116">Фильтрация передачи файлов влияет и на мгновенные сообщения и на конференции. Для последних данные настройки влияют на функцию выдачи в клиенте Office Live Meeting 2007 и функции воспроизведения мультимедиа файлов.</span><span class="sxs-lookup"><span data-stu-id="56578-p116">Filter transfer filtering affects both instant messages and conferences. For conferences, these settings affect the handout feature in the Office Live Meeting 2007 client and multimedia playback features.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="56578-166">Lync Server также предлагает варианты настройки передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="56578-166">Lync Server also offers file transfer setting options.</span></span> <span data-ttu-id="56578-167">Этот параметр на стороне сервера предлагается в дополнение к клиентским элементам управления, доступным в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="56578-167">This server-side option is offered in addition to the client-side controls available in Lync Server.</span></span>



</div>

<span data-ttu-id="56578-p118">Передачу файлов любых типов можно фильтровать во время обмена мгновенными сообщениям, при использовании функции выдачи в клиенте Office Live Meeting 2007 и во время воспроизведения мультимедиа файлов. Для контроля передачи файлов можно использовать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="56578-p118">You can filter file transfers during instant message conversations, when you are using the handout feature in the Office Live Meeting 2007 client, and for multimedia playback features for all file types. You can set the following options to control file transfers:</span></span>

  - <span data-ttu-id="56578-170">**Включение фильтра файлов**     Этот параметр включает фильтрацию файлов для глобального развертывания или для выбранного сайта.</span><span class="sxs-lookup"><span data-stu-id="56578-170">**Enable file filter**   This option enables file filtering for the global deployment or for the site that you select.</span></span>
    
    <span data-ttu-id="56578-171">При включении фильтра, можно выбрать один из следующих вариантов в поле **Передача файлов**:</span><span class="sxs-lookup"><span data-stu-id="56578-171">When you enable the file filter, you can choose one of the following options in **File transfer**:</span></span>
    
      - <span data-ttu-id="56578-172">**Блокировка определенных типов файлов**     Вы можете указать, какие запросы на передачу файлов фильтруются сервером, указав список блокируемых расширений файлов.</span><span class="sxs-lookup"><span data-stu-id="56578-172">**Block specific file types**   You specify which file transfer requests are filtered by the server by specifying a list of file extensions to block.</span></span> <span data-ttu-id="56578-173">Записи в списке могут содержать все стандартные символы, но не символ подстановки ( \* ).</span><span class="sxs-lookup"><span data-stu-id="56578-173">Entries in the list can contain all standard characters, but not the wildcard character (\*).</span></span> <span data-ttu-id="56578-174">В клиенте Office Live Meeting 2007 функция выдачи остается включенной, на любой файл с данным расширением нельзя загружать и отправлять.</span><span class="sxs-lookup"><span data-stu-id="56578-174">In the Office Live Meeting 2007 client the handout feature is enabled, but any file with this extension cannot be uploaded or downloaded.</span></span> <span data-ttu-id="56578-175">Если установить флажок **Блокировать URL-адреса с расширением файла**  на вкладке **URL-фильтр**, то URL-фильтр использует тот же список для блокировки активных гиперссылок, содержащих какое-либо из этих расширений.</span><span class="sxs-lookup"><span data-stu-id="56578-175">If you select the **Block URLs with file extension** check box on the settings for a URL filter listed on the **URL Filter** tab, the URL filter uses this same list to block active hyperlinks that contain any of these file extensions.</span></span> <span data-ttu-id="56578-176">Чтобы выбрать блокируемые типы файлов, нажмите **Выбрать** и затем  **Выбрать тип файла** и добавьте расширения к списку **Выбранные расширения типов файлов**.</span><span class="sxs-lookup"><span data-stu-id="56578-176">To choose which file types you want to block, click **Select**, and then, in **Select File Type**, add the file type extensions to the **Selected file type extensions** list.</span></span>
    
      - <span data-ttu-id="56578-177">**Заблокировать все**     Сервер удаляет все мгновенные сообщения, которые содержат запросы на передачу файлов, и возвращает сообщение об ошибке отправителю запроса.</span><span class="sxs-lookup"><span data-stu-id="56578-177">**Block All**   The server drops all instant messages that contain file transfer requests and returns an error message to the sender of the request.</span></span> <span data-ttu-id="56578-178">Функция выдачи в клиенте Office Live Meeting 2007 отключается.</span><span class="sxs-lookup"><span data-stu-id="56578-178">The handout feature in the Office Live Meeting 2007 client is disabled.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="56578-p121">Фильтрация расширений файлов ограничиваются стандартными именами. Фильтр может не работать с расширениями, внедренными в другие названия.</span><span class="sxs-lookup"><span data-stu-id="56578-p121">Filtering of file extensions is limited to standard file names. Filtering may not work with file extensions embedded in other names.</span></span>



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="56578-181">В данном подразделе</span><span class="sxs-lookup"><span data-stu-id="56578-181">In This Section</span></span>

  - [<span data-ttu-id="56578-182">Изменение фильтра передачи файлов по умолчанию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56578-182">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [<span data-ttu-id="56578-183">Создание нового фильтра передачи файлов в Lync Server 2013 для определенного сайта</span><span class="sxs-lookup"><span data-stu-id="56578-183">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [<span data-ttu-id="56578-184">Изменение фильтра URL-адресов по умолчанию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56578-184">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)

  - [<span data-ttu-id="56578-185">Создание нового фильтра URL-адресов в Lync Server 2013 для обработки гиперссылок в текстовых беседах</span><span class="sxs-lookup"><span data-stu-id="56578-185">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="56578-186">См. также</span><span class="sxs-lookup"><span data-stu-id="56578-186">See Also</span></span>


[<span data-ttu-id="56578-187">Управление параметрами обмена мгновенными сообщениями и сведениями о присутствии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56578-187">Managing IM and presence settings in Lync Server 2013</span></span>](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

