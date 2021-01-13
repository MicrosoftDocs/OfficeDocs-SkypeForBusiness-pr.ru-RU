---
title: Планирование парковки вызовов в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Планирование парковки вызовов в Skype для бизнеса Server Корпоративная голосовая связь, что позволяет помещать вызовы на удержание и переводить вызовы в отделы. Включает планирование мощности, поддерживаемые вызовы и поддерживаемые клиенты.
ms.openlocfilehash: c324e8d61f6d0e9e67870f05597a9157965a3eb3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825929"
---
# <a name="plan-for-call-park-in-skype-for-business"></a><span data-ttu-id="b5d69-104">Планирование парковки вызовов в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b5d69-104">Plan for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="b5d69-105">Планирование парковки вызовов в Skype для бизнеса Server Корпоративная голосовая связь, что позволяет помещать звонки на удержание и переводить вызовы в отделы.</span><span class="sxs-lookup"><span data-stu-id="b5d69-105">Planning for call park in Skype for Business Server Enterprise Voice, which enables putting calls on hold and transferring calls to departments.</span></span> <span data-ttu-id="b5d69-106">Включает планирование мощности, поддерживаемые вызовы и поддерживаемые клиенты.</span><span class="sxs-lookup"><span data-stu-id="b5d69-106">Includes capacity planning, supported calls, and supported clients.</span></span>
  
<span data-ttu-id="b5d69-107">Приложение парковки вызовов позволяет Корпоративная голосовая связь сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="b5d69-107">The Call Park application enables Enterprise Voice users to do the following:</span></span>
  
- <span data-ttu-id="b5d69-108">переводить вызов в режим удержания, а затем извлекать вызов на том же или другом телефоне;</span><span class="sxs-lookup"><span data-stu-id="b5d69-108">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>
    
- <span data-ttu-id="b5d69-109">переводить вызов в режим удержания для его переадресации в определенный отдел или область (например, в отдел продаж или склад, где есть телефон общего пользования).</span><span class="sxs-lookup"><span data-stu-id="b5d69-109">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>
    
- <span data-ttu-id="b5d69-110">переводить вызов в режим удержания и освобождать первоначальный телефон для других вызовов.</span><span class="sxs-lookup"><span data-stu-id="b5d69-110">Put a call on hold and keep the original answering phone free for other calls.</span></span>
    
<span data-ttu-id="b5d69-111">Когда пользователь паркует вызов, Skype для бизнеса Server переводит вызов на временный номер, называемый орбитой, где вызов удерживается до тех пор, пока он не будет извлечен или не будет разозваться. Skype для бизнеса Server отправляет орбиту пользователю, который припарковал вызов.</span><span class="sxs-lookup"><span data-stu-id="b5d69-111">When a user parks a call, Skype for Business Server transfers the call to a temporary number, called an orbit, where the call is held until it is retrieved or it times out. Skype for Business Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="b5d69-112">Чтобы извлечь вызов пользователь может набрать номер орбиты или щелкнуть ссылку орбиты или нажать кнопку в окне беседы.</span><span class="sxs-lookup"><span data-stu-id="b5d69-112">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span> 
  
<span data-ttu-id="b5d69-p104">Пользователь, который припарковал вызов, может уведомить кого-то для извлечения вызова с помощью внешнего механизма, например системы обмена мгновенными сообщениями или пейджинговой системы, для передачи номера орбиты другому пользователю. Пользователь, запарковавший вызов, может оставить окно беседы открытым, чтобы получить уведомление при извлечении вызова.</span><span class="sxs-lookup"><span data-stu-id="b5d69-p104">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else. The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>
  
<span data-ttu-id="b5d69-115">Так как диапазоны орбит являются глобально уникальными, можно получать звонки с любого сайта Skype для бизнеса Server или телефона УАПС, если маршруты настроены соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="b5d69-115">Because orbit ranges are globally unique, it is possible to retrieve calls from any Skype for Business Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="b5d69-116">Если никто не извлекает вызов в течение заданного промежутка времени, вызов возвращается пользователю, который его запарковал.</span><span class="sxs-lookup"><span data-stu-id="b5d69-116">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="b5d69-117">Если это лицо не отвечает на вызов, он переадресовывается на резервный номер, например оператору, если это настроено.</span><span class="sxs-lookup"><span data-stu-id="b5d69-117">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="b5d69-118">Вы можете настроить число попыток вызова первоначального пользователя от одного до десяти раз.</span><span class="sxs-lookup"><span data-stu-id="b5d69-118">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="b5d69-119">Если никто не отвечает на переадресованный вызов, он будет разъединен.</span><span class="sxs-lookup"><span data-stu-id="b5d69-119">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="b5d69-120">Орбита освобождается, когда вызов извлекается или отключается.</span><span class="sxs-lookup"><span data-stu-id="b5d69-120">The orbit is freed when the call is retrieved or disconnected.</span></span>
  
<span data-ttu-id="b5d69-121">При развертывании парковки вызовов необходимо зарезервировать диапазоны дополнительных номеров для парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="b5d69-121">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="b5d69-122">Эти расширения должны быть виртуальными расширениями: расширениями, для которых не назначен пользователь или телефон.</span><span class="sxs-lookup"><span data-stu-id="b5d69-122">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="b5d69-123">Затем необходимо настроить таблицу орбит парковки вызовов с диапазонами номеров и указать, в какой службе приложений размещено приложение парковки вызовов, которое обрабатывает каждый диапазон.</span><span class="sxs-lookup"><span data-stu-id="b5d69-123">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="b5d69-124">Каждый пул переднего сервера имеет таблицу парковки вызовов на соответствующем тыловом сервере, которая используется для управления вызовами, припаркованными в пуле.</span><span class="sxs-lookup"><span data-stu-id="b5d69-124">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="b5d69-125">Список диапазонов орбит хранится в центральном хранилище управления и используется для маршрутов орбит в пул назначения.</span><span class="sxs-lookup"><span data-stu-id="b5d69-125">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="b5d69-126">Каждый пул Skype для бизнеса Server, в котором развернуто и настроено приложение парковки вызовов, может иметь один или несколько диапазонов орбиты.</span><span class="sxs-lookup"><span data-stu-id="b5d69-126">Each Skype for Business Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="b5d69-127">Диапазоны орбит должны быть глобально уникальными в рамках развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b5d69-127">Orbit ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
<span data-ttu-id="b5d69-p107">Кроме того, вы настраиваете другие параметры парковки вызовов, например вы указываете, перенаправляются ли вызовы при истечении времени ожидания, и слышит ли абонент музыки, когда вызов припаркован. Вы также можете задать указать музыкальный файл, который воспроизводится, пока вызов находится на удержании.</span><span class="sxs-lookup"><span data-stu-id="b5d69-p107">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked. You can also specify the music file to play while the call is on hold.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b5d69-130">Настраиваемые файлы музыки при удержании для парковки вызовов не архивются в процессе аварийного восстановления Skype для бизнеса Server и будут потеряны, если файлы, загруженные в пул, будут повреждены или стираться.</span><span class="sxs-lookup"><span data-stu-id="b5d69-130">Customized music-on-hold files for Call Park are not backed up as part of the Skype for Business Server disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="b5d69-131">Всегда храните отдельную копию настраиваемых файлов музыки для вызовов в режиме удержания, загруженные для парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="b5d69-131">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span> 
  
<span data-ttu-id="b5d69-p109">Приложение парковки вызовов является компонентом Enterprise Voice. При развертывании Enterprise Voice приложение парковки вызовов устанавливается и активируется автоматически. Однако перед использованием парковки вызовов администратор должен настроить Enterprise Voice и включить эту функций для пользователей с помощью политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="b5d69-p109">The Call Park application is a component of Enterprise Voice. When you deploy Enterprise Voice, the Call Park application is installed and activated automatically. Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="b5d69-135">Развертывание и требования</span><span class="sxs-lookup"><span data-stu-id="b5d69-135">Deployment and requirements</span></span>

<span data-ttu-id="b5d69-136">Приложение парковки вызовов устанавливается автоматически при развертывании Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="b5d69-136">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="b5d69-137">Вы включаете парковку вызовов, настроив политику голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="b5d69-137">You enable Call Park by configuring voice policy.</span></span>
  
### <a name="software-requirements"></a><span data-ttu-id="b5d69-138">Требования к программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="b5d69-138">Software requirements</span></span>

<span data-ttu-id="b5d69-139">На всех серверах переднего сервера и серверах Standard Edition, на которых развернута служба парковки вызовов, должна быть установлена windows Media Format Runtime для серверов с Windows Server 2008 R2 или Microsoft Media Foundation для серверов под управлением Windows Server 2012 или Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="b5d69-139">All Front End Servers and Standard Edition servers where Call Park is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="b5d69-140">Для Windows Server 2008 R2 windows Media Format Runtime устанавливается как часть рабочего стола Windows.</span><span class="sxs-lookup"><span data-stu-id="b5d69-140">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="b5d69-141">Windows Media Format Runtime или Microsoft Media Foundation необходимы для файлов Windows Media Audio (WMA), которые парковка вызовов воспроизводит для музыки при удержании.</span><span class="sxs-lookup"><span data-stu-id="b5d69-141">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>
  
### <a name="port-requirements"></a><span data-ttu-id="b5d69-142">Требования к портам</span><span class="sxs-lookup"><span data-stu-id="b5d69-142">Port requirements</span></span>

<span data-ttu-id="b5d69-143">Приложение парковки вызовов использует **порт 5075 для**  запросов прослушивания SIP.</span><span class="sxs-lookup"><span data-stu-id="b5d69-143">The Call Park application uses **Port 5075**  for SIP listening requests.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b5d69-144">Этот порт является установкой по умолчанию, которую можно изменить с помощью командлета **Set-CsApplicationServer**.</span><span class="sxs-lookup"><span data-stu-id="b5d69-144">This port is a default setting that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="b5d69-145">Подробные сведения об этом cmdlet см. в документации по Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b5d69-145">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>
  
### <a name="audio-file-requirements"></a><span data-ttu-id="b5d69-146">Требования к аудиофайлам</span><span class="sxs-lookup"><span data-stu-id="b5d69-146">Audio File requirements</span></span>

<span data-ttu-id="b5d69-147">Приложение парковки вызовов поддерживает только файлы Windows Media Audio (WMA) для музыки на удержании.</span><span class="sxs-lookup"><span data-stu-id="b5d69-147">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="b5d69-148">С помощью Microsoft Expression Encoder 4 можно настроить файлы для музыки на удержании.</span><span class="sxs-lookup"><span data-stu-id="b5d69-148">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="b5d69-149">Чтобы скачать expression Encoder 4,   [см. "Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span><span class="sxs-lookup"><span data-stu-id="b5d69-149">To download Expression Encoder 4, see   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span></span> <span data-ttu-id="b5d69-150">Используйте это средство для преобразования файла в формат WMA.</span><span class="sxs-lookup"><span data-stu-id="b5d69-150">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="b5d69-151">Рекомендуемый формат для файлов музыки при удержании при парковке вызовов: Media Audio 9, 44 кГц, 16 бит, Моно, CBR, 32 кбайт/с.</span><span class="sxs-lookup"><span data-stu-id="b5d69-151">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b5d69-152">Преобразованный файл воспроизводится на телефоне только на 16 кГц, даже если он был записан на 44 кГц.</span><span class="sxs-lookup"><span data-stu-id="b5d69-152">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span> 
  
## <a name="supported-clients-and-calls"></a><span data-ttu-id="b5d69-153">Поддерживаемые клиенты и вызовы</span><span class="sxs-lookup"><span data-stu-id="b5d69-153">Supported clients and calls</span></span>

<span data-ttu-id="b5d69-154">Для парковки вызовов поддерживаются следующие клиенты и типы вызовов</span><span class="sxs-lookup"><span data-stu-id="b5d69-154">The following clients and types of calls are supported for Call Park</span></span>
  
### <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="b5d69-155">Клиенты, поддерживаемые для приостановки звонков</span><span class="sxs-lookup"><span data-stu-id="b5d69-155">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="b5d69-156">Приостанавливать можно звонки с любых IP-телефонов, АТС учреждения (УАТС), телефонной сети общего пользования (ТСОП) и с мобильных телефонов.</span><span class="sxs-lookup"><span data-stu-id="b5d69-156">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b5d69-p114">Приостанавливать можно только голосовые звонки. Приостанавливать сеансы обмена мгновенными сообщениями и конференции нельзя.</span><span class="sxs-lookup"><span data-stu-id="b5d69-p114">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span> 
  
<span data-ttu-id="b5d69-159">Следующие клиенты могут использовать парковку вызовов для парковки вызовов:</span><span class="sxs-lookup"><span data-stu-id="b5d69-159">The following clients can use Call Park to park calls:</span></span>
  
- <span data-ttu-id="b5d69-160">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b5d69-160">Skype for Business</span></span>
    
- <span data-ttu-id="b5d69-161">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="b5d69-161">Lync 2013</span></span>
    
- <span data-ttu-id="b5d69-162">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="b5d69-162">Lync 2010</span></span>
    
- <span data-ttu-id="b5d69-163">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="b5d69-163">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="b5d69-164">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="b5d69-164">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="b5d69-165">Мобильные телефоны не могут использовать парковку вызовов для парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="b5d69-165">Mobile phones cannot use Call Park to park calls.</span></span> 
  
### <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="b5d69-166">Клиенты, поддерживаемые для приема звонков</span><span class="sxs-lookup"><span data-stu-id="b5d69-166">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="b5d69-p115">Диапазоны орбит задаются в виде блоков виртуальных расширений (расширений без назначенных пользователей или телефонов). При настройке орбит в виде виртуальных расширений мобильные телефоны и телефоны ТСОП не смогут принимать приостановленные звонки.</span><span class="sxs-lookup"><span data-stu-id="b5d69-p115">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="b5d69-169">Федеративные пользователи не могут принимать приостановленные звонки.</span><span class="sxs-lookup"><span data-stu-id="b5d69-169">Federated users cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="b5d69-170">Следующие клиенты могут получать вызовы, припаркованные на парковке вызовов:</span><span class="sxs-lookup"><span data-stu-id="b5d69-170">The following clients can retrieve calls that are parked on Call Park:</span></span>
  
- <span data-ttu-id="b5d69-171">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b5d69-171">Skype for Business</span></span>
    
- <span data-ttu-id="b5d69-172">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="b5d69-172">Lync 2013</span></span>
    
- <span data-ttu-id="b5d69-173">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="b5d69-173">Lync 2010</span></span>
    
- <span data-ttu-id="b5d69-174">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="b5d69-174">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="b5d69-175">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="b5d69-175">Lync Phone Edition</span></span>
    
- <span data-ttu-id="b5d69-176">Региональные IP-телефоны</span><span class="sxs-lookup"><span data-stu-id="b5d69-176">IP common area phones</span></span>
    
- <span data-ttu-id="b5d69-177">Телефоны, не подключенные к инфраструктуре Skype для бизнеса Server, в том числе телефоны общего звонков и УАЧС</span><span class="sxs-lookup"><span data-stu-id="b5d69-177">Non-IP phones that are connected to the Skype for Business Server infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>
    
## <a name="call-park-capacity-planning"></a><span data-ttu-id="b5d69-178">Планирование емкости парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="b5d69-178">Call Park capacity planning</span></span>

<span data-ttu-id="b5d69-179">В следующей таблице описана пользовательская модель парковки вызовов, которую можно использовать в качестве основы для планирования емкости.</span><span class="sxs-lookup"><span data-stu-id="b5d69-179">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b5d69-180">Помните, что для планирования емкости аварийного восстановления каждый пул парного пула должен иметь возможность обрабатывать рабочие нагрузки для служб парковки вызовов в обоих пулах.</span><span class="sxs-lookup"><span data-stu-id="b5d69-180">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span> 
  
<span data-ttu-id="b5d69-181">**Пользовательская модель парковки вызовов**</span><span class="sxs-lookup"><span data-stu-id="b5d69-181">**Call Park User Model**</span></span>

|<span data-ttu-id="b5d69-182">**Метрика**</span><span class="sxs-lookup"><span data-stu-id="b5d69-182">**Metric**</span></span>|<span data-ttu-id="b5d69-183">**Для каждого пула переднего  <br/>  сервера (с 8 серверами переднего сервера)**</span><span class="sxs-lookup"><span data-stu-id="b5d69-183">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="b5d69-184">**Для каждого сервера Standard Edition**</span><span class="sxs-lookup"><span data-stu-id="b5d69-184">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b5d69-185">Скорость парковки</span><span class="sxs-lookup"><span data-stu-id="b5d69-185">Park rate</span></span>  <br/> |<span data-ttu-id="b5d69-186">8 вызовов в минуту</span><span class="sxs-lookup"><span data-stu-id="b5d69-186">8 per minute</span></span>  <br/> |<span data-ttu-id="b5d69-187">1 вызов в минуту</span><span class="sxs-lookup"><span data-stu-id="b5d69-187">1 per minute</span></span>  <br/> |
|<span data-ttu-id="b5d69-188">Скорость извлечения паркованных вызовов</span><span class="sxs-lookup"><span data-stu-id="b5d69-188">Retrieve parked call rate</span></span>  <br/> |<span data-ttu-id="b5d69-189">8 вызовов в минуту</span><span class="sxs-lookup"><span data-stu-id="b5d69-189">8 per minute</span></span>  <br/> |<span data-ttu-id="b5d69-190">1 вызов в минуту</span><span class="sxs-lookup"><span data-stu-id="b5d69-190">1 per minute</span></span>  <br/> |
|<span data-ttu-id="b5d69-191">Среднее время парковки</span><span class="sxs-lookup"><span data-stu-id="b5d69-191">Average park duration</span></span>  <br/> |<span data-ttu-id="b5d69-192">60 секунд</span><span class="sxs-lookup"><span data-stu-id="b5d69-192">60 seconds</span></span>  <br/> |<span data-ttu-id="b5d69-193">60 секунд</span><span class="sxs-lookup"><span data-stu-id="b5d69-193">60 seconds</span></span>  <br/> |
   

