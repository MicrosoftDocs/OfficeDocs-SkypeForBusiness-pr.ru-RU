---
title: Планирование парковки вызовов в Skype для бизнеса 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Планирование для парковки вызовов в Скайп Business Server корпоративной голосовой связи, что позволяет размещение звонков на удержание и передача вызовов для отделов. Включает планирование мощности, поддерживаемые вызовы и поддерживаемые клиенты.
ms.openlocfilehash: 71166aa866f2242248dc090da19212a5e1122161
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-call-park-in-skype-for-business-2015"></a><span data-ttu-id="5b71b-104">Планирование парковки вызовов в Skype для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="5b71b-104">Plan for Call Park in Skype for Business 2015</span></span>
 
<span data-ttu-id="5b71b-105">Планирование для парковки вызовов в Скайп Business Server корпоративной голосовой связи, что позволяет размещение звонков на удержание и передача вызовов для отделов.</span><span class="sxs-lookup"><span data-stu-id="5b71b-105">Planning for call park in Skype for Business Server Enterprise Voice, which enables putting calls on hold and transferring calls to departments.</span></span> <span data-ttu-id="5b71b-106">Включает планирование мощности, поддерживаемые вызовы и поддерживаемые клиенты.</span><span class="sxs-lookup"><span data-stu-id="5b71b-106">Includes capacity planning, supported calls, and supported clients.</span></span>
  
<span data-ttu-id="5b71b-107">Приложение парковки вызовов позволяет пользователям корпоративной голосовой связи выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="5b71b-107">The Call Park application enables Enterprise Voice users to do the following:</span></span>
  
- <span data-ttu-id="5b71b-108">переводить вызов в режим удержания, а затем извлекать вызов на том же или другом телефоне;</span><span class="sxs-lookup"><span data-stu-id="5b71b-108">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>
    
- <span data-ttu-id="5b71b-109">переводить вызов в режим удержания для его переадресации в определенный отдел или область (например, в отдел продаж или склад, где есть телефон общего пользования).</span><span class="sxs-lookup"><span data-stu-id="5b71b-109">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>
    
- <span data-ttu-id="5b71b-110">переводить вызов в режим удержания и освобождать первоначальный телефон для других вызовов.</span><span class="sxs-lookup"><span data-stu-id="5b71b-110">Put a call on hold and keep the original answering phone free for other calls.</span></span>
    
<span data-ttu-id="5b71b-111">Когда пользователь парков звонка, Скайп для Business Server переводит вызов на временной номер, называемый орбиты, где вызова удерживается до получения или истечения времени ожидания. Скайп для Business Server отправляет орбиты пользователя, который приостанавливать звонок.</span><span class="sxs-lookup"><span data-stu-id="5b71b-111">When a user parks a call, Skype for Business Server transfers the call to a temporary number, called an orbit, where the call is held until it is retrieved or it times out. Skype for Business Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="5b71b-112">Чтобы извлечь вызов, пользователь может набрать номер орбиты или щелкнуть ссылку орбиты или нажать кнопку в окне беседы.</span><span class="sxs-lookup"><span data-stu-id="5b71b-112">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span> 
  
<span data-ttu-id="5b71b-p104">Пользователь, который припарковал вызов, может уведомить кого-то для извлечения вызова с помощью внешнего механизма, например системы обмена мгновенными сообщениями или пейджинговой системы, для передачи номера орбиты другому пользователю. Пользователь, запарковавший вызов, может оставить окно беседы открытым, чтобы получить уведомление при извлечении вызова.</span><span class="sxs-lookup"><span data-stu-id="5b71b-p104">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else. The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>
  
<span data-ttu-id="5b71b-115">Поскольку диапазонов орбит глобальный уникальный, можно получить звонки из любого Скайп для сайта Business Server или телефон УАТС, если маршрутизация настроен соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="5b71b-115">Because orbit ranges are globally unique, it is possible to retrieve calls from any Skype for Business Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="5b71b-116">Если никто не извлекает вызов в течение заданного промежутка времени, вызов возвращается пользователю, который его запарковал.</span><span class="sxs-lookup"><span data-stu-id="5b71b-116">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="5b71b-117">Если это лицо не отвечает на вызов, он переадресовывается на резервный номер, например оператору, если это настроено.</span><span class="sxs-lookup"><span data-stu-id="5b71b-117">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="5b71b-118">Вы можете настроить число попыток вызова первоначального пользователя от одного до десяти раз.</span><span class="sxs-lookup"><span data-stu-id="5b71b-118">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="5b71b-119">Если никто не отвечает на переадресованный вызов, он будет разъединен.</span><span class="sxs-lookup"><span data-stu-id="5b71b-119">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="5b71b-120">Орбита освобождается, когда вызов извлекается или отключается.</span><span class="sxs-lookup"><span data-stu-id="5b71b-120">The orbit is freed when the call is retrieved or disconnected.</span></span>
  
<span data-ttu-id="5b71b-121">Во время развертывания парковки вызовов, необходимо зарезервировать диапазоны добавочных номеров для парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="5b71b-121">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="5b71b-122">Файлы с этим расширением должны быть виртуального расширения: расширения, которые не имеют пользователя или назначен телефон.</span><span class="sxs-lookup"><span data-stu-id="5b71b-122">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="5b71b-123">Затем Настройка таблицы орбиты парковки вызовов с диапазонами добавочные номера и указать, какие службы приложения, где размещается приложение парковки вызовов, обрабатывающий каждого диапазона.</span><span class="sxs-lookup"><span data-stu-id="5b71b-123">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="5b71b-124">Каждый пул переднего плана используется таблица, парковки вызовов на соответствующий фоновый сервер, используемый для управления звонки, приостановленные в пуле.</span><span class="sxs-lookup"><span data-stu-id="5b71b-124">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="5b71b-125">В центре управления хранится список диапазонов орбит хранения и используется для маршрутизации орбиты в конечном пуле.</span><span class="sxs-lookup"><span data-stu-id="5b71b-125">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="5b71b-126">Каждый Скайп для пула Business Server, где развернута и настроена приложения приостановки звонков может иметь один или несколько диапазонов орбит.</span><span class="sxs-lookup"><span data-stu-id="5b71b-126">Each Skype for Business Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="5b71b-127">Диапазоны орбит значения глобальный уникальный через Скайп для развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="5b71b-127">Orbit ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
<span data-ttu-id="5b71b-p107">Кроме того, вы настраиваете другие параметры парковки вызовов, например вы указываете, перенаправляются ли вызовы при истечении времени ожидания и слышит ли абонент музыку, когда вызов припаркован. Вы также можете задать указать музыкальный файл, который воспроизводится, пока вызов находится на удержании.</span><span class="sxs-lookup"><span data-stu-id="5b71b-p107">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked. You can also specify the music file to play while the call is on hold.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5b71b-130">Настроенные файлы музыки при удержании для парковки вызовов без резервных копий как часть Скайп для процесса аварийного восстановления Business Server и будут потеряны, если поврежден, повреждены или удалены файлы, загруженные в пул.</span><span class="sxs-lookup"><span data-stu-id="5b71b-130">Customized music-on-hold files for Call Park are not backed up as part of the Skype for Business Server disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="5b71b-131">Всегда храните отдельную копию настраиваемых файлов музыки для вызовов в режиме удержания, загруженные для парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="5b71b-131">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span> 
  
<span data-ttu-id="5b71b-132">Приложение парковки вызовов является компонентом системы корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="5b71b-132">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="5b71b-133">При развертывании корпоративной голосовой связи, приложение парковки вызовов устанавливается и активируется автоматически.</span><span class="sxs-lookup"><span data-stu-id="5b71b-133">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="5b71b-134">Прежде чем использовать парковки вызовов, тем не менее, администратор корпоративной голосовой связи необходимо настроить его и включить для пользователей с помощью политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="5b71b-134">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="5b71b-135">Развертывание и требования</span><span class="sxs-lookup"><span data-stu-id="5b71b-135">Deployment and requirements</span></span>

<span data-ttu-id="5b71b-136">Приложение парковки вызовов устанавливается автоматически при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="5b71b-136">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="5b71b-137">Включение парковки вызовов, настроив политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="5b71b-137">You enable Call Park by configuring voice policy.</span></span>
  
### <a name="software-requirements"></a><span data-ttu-id="5b71b-138">Требования к программному обеспечению </span><span class="sxs-lookup"><span data-stu-id="5b71b-138">Software requirements</span></span>

<span data-ttu-id="5b71b-139">Все серверы переднего плана и Standard Edition серверы, где развернут парковки вызовов, должны использовать среда выполнения установки для серверов под управлением Windows Server 2008 R2 или Microsoft Foundation мультимедиа для серверов под управлением Windows Server 2012 или Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="5b71b-139">All Front End Servers and Standard Edition servers where Call Park is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="5b71b-140">Для Windows Server 2008 R2 среда выполнения устанавливается как часть рабочего стола Windows.</span><span class="sxs-lookup"><span data-stu-id="5b71b-140">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="5b71b-141">Среда выполнения Microsoft Foundation мультимедиа необходима Windows Media Audio (с расширением WMA) файлы, которые воспроизводит парковки вызовов для музыки при удержании.</span><span class="sxs-lookup"><span data-stu-id="5b71b-141">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>
  
### <a name="port-requirements"></a><span data-ttu-id="5b71b-142">Требования к портам</span><span class="sxs-lookup"><span data-stu-id="5b71b-142">Port requirements</span></span>

<span data-ttu-id="5b71b-143">Приложение парковки вызовов использует **порт 5075** для запросов прослушивания.</span><span class="sxs-lookup"><span data-stu-id="5b71b-143">The Call Park application uses **Port 5075**  for SIP listening requests.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5b71b-144">Этот порт — это значение по умолчанию, который можно изменить с помощью командлета **Set-CsApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="5b71b-144">This port is a default setting that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="5b71b-145">Для получения дополнительных сведений о этого командлета обратитесь к документации Командная консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5b71b-145">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>
  
### <a name="audio-file-requirements"></a><span data-ttu-id="5b71b-146">Требования к звуковым файлам</span><span class="sxs-lookup"><span data-stu-id="5b71b-146">Audio File requirements</span></span>

<span data-ttu-id="5b71b-147">Парковка вызовов, которые приложение поддерживает только файлы Windows Media Audio (с расширением WMA) для музыки на удержание.</span><span class="sxs-lookup"><span data-stu-id="5b71b-147">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="5b71b-148">Чтобы настроить файлы для воспроизведения в качестве музыки в режиме удержания, можно использовать Microsoft Expression Encoder 4.</span><span class="sxs-lookup"><span data-stu-id="5b71b-148">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="5b71b-149">Чтобы загрузить 4 кодировщика выражение, обратитесь к разделу [«Кодировщика Expression 4»](https://go.microsoft.com/fwlink/p/?linkId=202843).</span><span class="sxs-lookup"><span data-stu-id="5b71b-149">To download Expression Encoder 4, see   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span></span> <span data-ttu-id="5b71b-150">Это средство используется для преобразования файлов в формат WMA.</span><span class="sxs-lookup"><span data-stu-id="5b71b-150">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="5b71b-151">Рекомендуемый формат для файлов музыки при удержании парковки вызовов — Media Audio 9, 44 кГц, 16 бит, моно, CBR 32 Кбит/с.</span><span class="sxs-lookup"><span data-stu-id="5b71b-151">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5b71b-152">Преобразованный файл воспроизводится на телефоне только при 16 кГц, даже если он был записан при 44 кГц.</span><span class="sxs-lookup"><span data-stu-id="5b71b-152">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span> 
  
## <a name="supported-clients-and-calls"></a><span data-ttu-id="5b71b-153">Поддерживаемые клиенты и вызовы</span><span class="sxs-lookup"><span data-stu-id="5b71b-153">Supported clients and calls</span></span>

<span data-ttu-id="5b71b-154">Следующие клиенты и типов вызовов, поддерживаемые для парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="5b71b-154">The following clients and types of calls are supported for Call Park</span></span>
  
### <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="5b71b-155">Клиенты, поддерживаемые для приостановки звонков</span><span class="sxs-lookup"><span data-stu-id="5b71b-155">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="5b71b-156">Приостанавливать можно звонки с любых IP-телефонов, АТС учреждения (УАТС), телефонной сети общего пользования (ТСОП) и с мобильных телефонов.</span><span class="sxs-lookup"><span data-stu-id="5b71b-156">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5b71b-p114">Приостанавливать можно только голосовые звонки. Приостанавливать сеансы обмена мгновенными сообщениями и конференции нельзя.</span><span class="sxs-lookup"><span data-stu-id="5b71b-p114">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span> 
  
<span data-ttu-id="5b71b-159">Следующие клиенты могут использовать парковки вызовов для приостановки звонков:</span><span class="sxs-lookup"><span data-stu-id="5b71b-159">The following clients can use Call Park to park calls:</span></span>
  
- <span data-ttu-id="5b71b-160">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="5b71b-160">Skype for Business</span></span>
    
- <span data-ttu-id="5b71b-161">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="5b71b-161">Lync 2013</span></span>
    
- <span data-ttu-id="5b71b-162">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="5b71b-162">Lync 2010</span></span>
    
- <span data-ttu-id="5b71b-163">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="5b71b-163">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="5b71b-164">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="5b71b-164">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="5b71b-165">Мобильные телефоны не могут использовать парковки вызовов для приостановки звонков.</span><span class="sxs-lookup"><span data-stu-id="5b71b-165">Mobile phones cannot use Call Park to park calls.</span></span> 
  
### <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="5b71b-166">Клиенты, поддерживаемые для приема звонков</span><span class="sxs-lookup"><span data-stu-id="5b71b-166">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="5b71b-p115">Диапазоны орбит задаются в виде блоков виртуальных расширений (расширений без назначенных пользователей или телефонов). При настройке орбит в виде виртуальных расширений мобильные телефоны и телефоны ТСОП не смогут принимать приостановленные звонки.</span><span class="sxs-lookup"><span data-stu-id="5b71b-p115">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="5b71b-169">Федеративные пользователи не могут принимать приостановленные звонки.</span><span class="sxs-lookup"><span data-stu-id="5b71b-169">Federated users cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="5b71b-170">Следующие клиенты могут принимать звонки, приостановленные в парковки вызовов:</span><span class="sxs-lookup"><span data-stu-id="5b71b-170">The following clients can retrieve calls that are parked on Call Park:</span></span>
  
- <span data-ttu-id="5b71b-171">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="5b71b-171">Skype for Business</span></span>
    
- <span data-ttu-id="5b71b-172">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="5b71b-172">Lync 2013</span></span>
    
- <span data-ttu-id="5b71b-173">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="5b71b-173">Lync 2010</span></span>
    
- <span data-ttu-id="5b71b-174">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="5b71b-174">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="5b71b-175">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="5b71b-175">Lync Phone Edition</span></span>
    
- <span data-ttu-id="5b71b-176">Региональные IP-телефоны</span><span class="sxs-lookup"><span data-stu-id="5b71b-176">IP common area phones</span></span>
    
- <span data-ttu-id="5b71b-177">Отличные от IP телефоны, подключенные к Скайп для инфраструктуры Business Server, включая региональные телефоны и относиться УАТС телефоны</span><span class="sxs-lookup"><span data-stu-id="5b71b-177">Non-IP phones that are connected to the Skype for Business Server infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>
    
## <a name="call-park-capacity-planning"></a><span data-ttu-id="5b71b-178">Планирование емкости для парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="5b71b-178">Call Park capacity planning</span></span>

<span data-ttu-id="5b71b-179">В следующей таблице описывается пользовательская модель парковки вызовов, которые можно использовать в качестве основы для планирования требований к мощности.</span><span class="sxs-lookup"><span data-stu-id="5b71b-179">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5b71b-180">Имейте в виду, что для планировании мощности аварийного восстановления, каждый пул, входящий в состав парного пула должна появиться возможность обрабатывать рабочие нагрузки служб парковки вызовов в обоих пулах.</span><span class="sxs-lookup"><span data-stu-id="5b71b-180">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span> 
  
<span data-ttu-id="5b71b-181">**Пользовательская модель парковки вызовов**</span><span class="sxs-lookup"><span data-stu-id="5b71b-181">**Call Park User Model**</span></span>

|<span data-ttu-id="5b71b-182">**Метрики**</span><span class="sxs-lookup"><span data-stu-id="5b71b-182">**Metric**</span></span>|<span data-ttu-id="5b71b-183">**Каждого пула переднего плана <br/> (содержит 8 серверов переднего плана)**</span><span class="sxs-lookup"><span data-stu-id="5b71b-183">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="5b71b-184">**На каждом сервере Standard Edition**</span><span class="sxs-lookup"><span data-stu-id="5b71b-184">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5b71b-185">Скорость парковки</span><span class="sxs-lookup"><span data-stu-id="5b71b-185">Park rate</span></span>  <br/> |<span data-ttu-id="5b71b-186">8 вызов в минуту</span><span class="sxs-lookup"><span data-stu-id="5b71b-186">8 per minute</span></span>  <br/> |<span data-ttu-id="5b71b-187">1 вызов в минуту</span><span class="sxs-lookup"><span data-stu-id="5b71b-187">1 per minute</span></span>  <br/> |
|<span data-ttu-id="5b71b-188">Скорость извлечения приостановленных вызовов</span><span class="sxs-lookup"><span data-stu-id="5b71b-188">Retrieve parked call rate</span></span>  <br/> |<span data-ttu-id="5b71b-189">8 вызов в минуту</span><span class="sxs-lookup"><span data-stu-id="5b71b-189">8 per minute</span></span>  <br/> |<span data-ttu-id="5b71b-190">1 вызов в минуту</span><span class="sxs-lookup"><span data-stu-id="5b71b-190">1 per minute</span></span>  <br/> |
|<span data-ttu-id="5b71b-191">Среднее время парковки</span><span class="sxs-lookup"><span data-stu-id="5b71b-191">Average park duration</span></span>  <br/> |<span data-ttu-id="5b71b-192">60 с</span><span class="sxs-lookup"><span data-stu-id="5b71b-192">60 seconds</span></span>  <br/> |<span data-ttu-id="5b71b-193">60 с</span><span class="sxs-lookup"><span data-stu-id="5b71b-193">60 seconds</span></span>  <br/> |
   

