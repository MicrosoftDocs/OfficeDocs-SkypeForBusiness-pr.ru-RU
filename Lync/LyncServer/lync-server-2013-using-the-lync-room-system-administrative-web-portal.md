---
title: 'Lync Server 2013: использование веб-портала администрирования системы комнат Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d950bd62b2db91f60dd5828f79977472a9c5d573
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="233f5-102">Использование веб-портала администрирования системы комнат Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="233f5-102">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="233f5-103">_**Последнее изменение темы:** 2014-11-10_</span><span class="sxs-lookup"><span data-stu-id="233f5-103">_**Topic Last Modified:** 2014-11-10_</span></span>

<span data-ttu-id="233f5-104">После развертывания LRS на сервере можно проверить состояние всех комнат LRS, войдя на веб-портал администрирования LRS из браузера.</span><span class="sxs-lookup"><span data-stu-id="233f5-104">After you deploy LRS on the server, you can check the status of all LRS rooms by signing into the LRS Administrative Web Portal from a browser.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="233f5-105">Вход</span><span class="sxs-lookup"><span data-stu-id="233f5-105">Sign in</span></span>

1.  <span data-ttu-id="233f5-106">Перейдите по следующему URL-адресу:</span><span class="sxs-lookup"><span data-stu-id="233f5-106">Browse to the following URL:</span></span>
    
    <span data-ttu-id="233f5-107">https://\<Fe Server\>/ЛРС</span><span class="sxs-lookup"><span data-stu-id="233f5-107">https://\<fe-server\>/lrs</span></span>

2.  <span data-ttu-id="233f5-108">Введите учетные данные для учетной записи LRSSupport или учетной записи, которая была добавлена в группу безопасности LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="233f5-108">Enter the credentials for the LRSSupport account or an account that has been added to the LRSSupportAdminGroup security group.</span></span>

<span data-ttu-id="233f5-109">![Экран входа на портал администрирования системы комнат Lync](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Экран входа на портал администрирования системы комнат Lync")</span><span class="sxs-lookup"><span data-stu-id="233f5-109">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a><span data-ttu-id="233f5-110">Сводная страница веб-портала LRS администрирования</span><span class="sxs-lookup"><span data-stu-id="233f5-110">LRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="233f5-111">На странице сводки представлены следующие сведения обо всех комнатах LRS, развернутых на сервере.</span><span class="sxs-lookup"><span data-stu-id="233f5-111">The summary page provides the following information for all of the LRS rooms deployed on the server:</span></span>

  - <span data-ttu-id="233f5-112">**Пометьте**   настраиваемое имя, которое администратор предоставляет в комнате.</span><span class="sxs-lookup"><span data-stu-id="233f5-112">**Tag**   The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="233f5-113">Тег можно задать в портале, щелкнув имя комнаты.</span><span class="sxs-lookup"><span data-stu-id="233f5-113">The Tag can be set in the portal by clicking on the room name.</span></span>

  - <span data-ttu-id="233f5-114">**Работоспособность**   состояние работоспособности комнаты, которая является производной от сводного состояния работоспособности комнаты, которая отображается в разделе работоспособность на странице "Параметры комнаты".</span><span class="sxs-lookup"><span data-stu-id="233f5-114">**Health**   The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

  - <span data-ttu-id="233f5-115">**Следующее собрание**   Дата и время, когда следующее собрание запланировано.</span><span class="sxs-lookup"><span data-stu-id="233f5-115">**Next Meeting**   The date and time the next meeting is scheduled.</span></span>

  - <span data-ttu-id="233f5-116">**LRS Version, Manufacturer, Model**   эти значения предопределены в LRS.</span><span class="sxs-lookup"><span data-stu-id="233f5-116">**LRS Version, Manufacturer, Model**   These values are preset in LRS.</span></span> <span data-ttu-id="233f5-117">В зависимости от производителя эти поля могут оставаться пустыми.</span><span class="sxs-lookup"><span data-stu-id="233f5-117">Depending on the manufacturer, these fields might be left blank.</span></span>

  - <span data-ttu-id="233f5-118">**Последнее обновление**   отображает время последнего обновления веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="233f5-118">**Last Refresh**   Displays the last time the webpage was refreshed.</span></span>

<span data-ttu-id="233f5-119">![Представление сводки портала администрирования системы комнат Lync](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Представление сводки портала администрирования системы комнат Lync")</span><span class="sxs-lookup"><span data-stu-id="233f5-119">![Lync Room System Admin Portal Summary View](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync Room System Admin Portal Summary View")</span></span>

</div>

<div>

## <a name="lrs-room-information"></a><span data-ttu-id="233f5-120">Сведения о комнате LRS</span><span class="sxs-lookup"><span data-stu-id="233f5-120">LRS Room Information</span></span>

<span data-ttu-id="233f5-121">Раздел сведения о комнате портала позволяет просматривать и настраивать отдельные комнаты LRS.</span><span class="sxs-lookup"><span data-stu-id="233f5-121">The Room Info section of the portal allows you to view and configure individual LRS rooms.</span></span> <span data-ttu-id="233f5-122">Он содержит четыре раздела: Settings, Details, устранение неполадок и работоспособность.</span><span class="sxs-lookup"><span data-stu-id="233f5-122">It contains four sections: Settings, Details, Troubleshooting, and Health.</span></span>

<div>

## <a name="settings"></a><span data-ttu-id="233f5-123">Параметры</span><span class="sxs-lookup"><span data-stu-id="233f5-123">Settings</span></span>

<span data-ttu-id="233f5-124">В разделе Параметры можно задать пароль, тег комнаты и уровни громкости по умолчанию для комнаты.</span><span class="sxs-lookup"><span data-stu-id="233f5-124">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="233f5-125">Если вы настроили эти параметры, изменения реплицируются только после перезапуска консоли LRS.</span><span class="sxs-lookup"><span data-stu-id="233f5-125">If you configure these settings, the changes are replicated only after you restart the LRS console.</span></span> <span data-ttu-id="233f5-126">Вы увидите только параметры обновления системы для систем комнат Lync версии 15,12 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="233f5-126">You will only see System Updates settings for Lync Room Systems that are version 15.12 and later.</span></span>

<span data-ttu-id="233f5-127">![Параметры комнаты портала администрирования системы комнат Lync](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Параметры комнаты портала администрирования системы комнат Lync")</span><span class="sxs-lookup"><span data-stu-id="233f5-127">![Lync Room System Admin Portal Room Settings](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync Room System Admin Portal Room Settings")</span></span>

</div>

<div>

## <a name="details"></a><span data-ttu-id="233f5-128">Сведения</span><span class="sxs-lookup"><span data-stu-id="233f5-128">Details</span></span>

<span data-ttu-id="233f5-129">В разделе Details (сведения) представлена сводная информация о параметрах комнаты LRS "только чтение", включая время последнего обновления; следующее собрание; Последние обновления, Обслуживание и калибровка; Параметры динамика, микрофона и абонента по умолчанию; Отслеживание УНИВЕРСАЛЬНЫЙ КОД РЕСУРСА (URI) SIP; Количество экранов и подробные сведения о каждом экране; состояние и действие.</span><span class="sxs-lookup"><span data-stu-id="233f5-129">The Details section provides a read-only summary of the LRS room’s settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

<span data-ttu-id="233f5-130">![Подробное представление портала администрирования системы комнат Lync](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Подробное представление портала администрирования системы комнат Lync")</span><span class="sxs-lookup"><span data-stu-id="233f5-130">![Lync Room System Admin Portal Detail View](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync Room System Admin Portal Detail View")</span></span>

</div>

<div>

## <a name="troubleshooting"></a><span data-ttu-id="233f5-131">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="233f5-131">Troubleshooting</span></span>

<span data-ttu-id="233f5-132">Раздел "Устранение неполадок" можно использовать для удаленного сбора журналов и их сохранения в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="233f5-132">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="233f5-133">Вы также можете перезапустить консоль LRS (пользовательский интерфейс LRS) или перезапустить всю систему.</span><span class="sxs-lookup"><span data-stu-id="233f5-133">You can also restart the LRS console (LRS user interface) or restart the entire system.</span></span> <span data-ttu-id="233f5-134">Чтобы собрать журналы, укажите путь к папке в указанном формате и убедитесь, что в папке есть разрешения на запись, предоставленные учетной записи компьютера LRS.</span><span class="sxs-lookup"><span data-stu-id="233f5-134">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the LRS machine account.</span></span> <span data-ttu-id="233f5-135">Если размер журнала слишком велик, может потребоваться до 5 минут для завершения сбора журналов.</span><span class="sxs-lookup"><span data-stu-id="233f5-135">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="233f5-136">После обновления страницы вы получите Последнее состояние.</span><span class="sxs-lookup"><span data-stu-id="233f5-136">Refreshing the page will give you the latest status.</span></span>

<span data-ttu-id="233f5-137">![Ведение журнала для комнаты портала администрирования системы комнат Lync](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Ведение журнала для комнаты портала администрирования системы комнат Lync")</span><span class="sxs-lookup"><span data-stu-id="233f5-137">![Lync Room System Admin Portal Room Logging](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync Room System Admin Portal Room Logging")</span></span>

</div>

<div>

## <a name="health"></a><span data-ttu-id="233f5-138">Здравоохранение</span><span class="sxs-lookup"><span data-stu-id="233f5-138">Health</span></span>

<span data-ttu-id="233f5-139">Раздел Health дает визуальную индикацию о работоспособности подключения к серверу Lync, звуковое устройство, видеоустройство, состояние устойчивости и устройство отображения.</span><span class="sxs-lookup"><span data-stu-id="233f5-139">The Health section gives a visual indication of the health of the Lync Server connection, audio device, video device, resiliency state, and screen device.</span></span>

<span data-ttu-id="233f5-140">![Работоспособность комнаты портала администрирования системы комнат Lync](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Работоспособность комнаты портала администрирования системы комнат Lync")</span><span class="sxs-lookup"><span data-stu-id="233f5-140">![Lync Room System Admin Portal Room Health](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync Room System Admin Portal Room Health")</span></span>

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="233f5-141">Дополнительные заметки о веб-портале администрирования</span><span class="sxs-lookup"><span data-stu-id="233f5-141">Additional Notes about the Administrative Web Portal</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="233f5-142">Изменения параметров применяются только после перезапуска системы LRS.</span><span class="sxs-lookup"><span data-stu-id="233f5-142">Setting changes are applied only after the LRS system is restarted.</span></span></P>
> <LI>
> <P><span data-ttu-id="233f5-143">Если срок действия пароля учетной записи Lrsapp включена поддержка истечет, состояние комнат будет недоступно.</span><span class="sxs-lookup"><span data-stu-id="233f5-143">If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="233f5-144">Настройте пароль учетной записи Лрсаппусер, чтобы он никогда не истекал, или не забудьте обновить пароль, если срок его действия приближается к концу.</span><span class="sxs-lookup"><span data-stu-id="233f5-144">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it’s near expiration.</span></span></P>
> <LI>
> <P><span data-ttu-id="233f5-145">Веб-портал администрирования LRS поддерживается только для локальных развертываний.</span><span class="sxs-lookup"><span data-stu-id="233f5-145">The LRS administrative web portal is supported for on-premises deployments only.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="233f5-146">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="233f5-146">Frequently Asked Questions</span></span>

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="233f5-147">Почему я не могу войти на веб-портал администрирования?</span><span class="sxs-lookup"><span data-stu-id="233f5-147">Why can’t I sign in to the administrative web portal?</span></span>

  - <span data-ttu-id="233f5-148">Когда вы открываете https://localhost/lrsстраницу входа, вы сможете увидеть страницу входа, но при вводе учетных данных вы не сможете войти в систему.</span><span class="sxs-lookup"><span data-stu-id="233f5-148">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="233f5-149">В этом случае необходимо открыть https://FQDNofFEserver/lrs для входа на веб-портал администрирования.</span><span class="sxs-lookup"><span data-stu-id="233f5-149">In this case, you must open https://FQDNofFEserver/lrs to sign in to the administrative web portal.</span></span>

  - <span data-ttu-id="233f5-150">Если компьютер, с которого осуществляется доступ к веб-порталу администрирования, находится в Рабочей группе, то "http://" не будет работать.</span><span class="sxs-lookup"><span data-stu-id="233f5-150">If the machine from which you are accessing the administrative web portal is in a workgroup, "http://" will not work.</span></span> <span data-ttu-id="233f5-151">Вместо этого используйте "HTTPS".</span><span class="sxs-lookup"><span data-stu-id="233f5-151">Use "https" instead.</span></span>

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="233f5-152">Почему я не вижу LRS на веб-портале администрирования?</span><span class="sxs-lookup"><span data-stu-id="233f5-152">Why can’t I see LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="233f5-153">Убедитесь, что у вас есть учетные записи LRS в развертывании, и они созданы в соответствии с рекомендациями по развертыванию веб-портала LRS.</span><span class="sxs-lookup"><span data-stu-id="233f5-153">Make sure you have LRS accounts in your deployment and that they are created according to the LRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="233f5-154">Убедитесь, что учетные записи LRS подготовлены с помощью команды Enable — CsMeetingRoom, а не Enable — CsUser на сервере Lync Server.</span><span class="sxs-lookup"><span data-stu-id="233f5-154">Make sure the LRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Lync server.</span></span>

  - <span data-ttu-id="233f5-155">Если вы создали учетные записи LRS и не видите учетные записи на веб-портале администрирования, соберите журналы сервера с помощью средства ведения журнала Lync Server с выбранным компонентом **митингпортал** , а затем отправьте их в контакт службы поддержки LRS.</span><span class="sxs-lookup"><span data-stu-id="233f5-155">If you have created LRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Lync Server Logging tool with the **MeetingPortal** component selected, and then send them to your LRS support contact.</span></span>

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="233f5-156">Почему на веб-портале администрирования не отображается состояние LRS?</span><span class="sxs-lookup"><span data-stu-id="233f5-156">Why can’t I see the status of LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="233f5-157">Убедитесь, что учетная запись пользователя Lrsapp включена поддержка включена для SIP.</span><span class="sxs-lookup"><span data-stu-id="233f5-157">Make sure that the LRSApp user account is SIP-enabled.</span></span>

  - <span data-ttu-id="233f5-158">Если у вас по-прежнему возникают проблемы, соберите файл **Trace. log** в системе LRS с D\\:\\Tracing\\лрсадминлогс, а затем отправьте его контакту службы поддержки LRS.</span><span class="sxs-lookup"><span data-stu-id="233f5-158">If you are still having issues, collect the **Trace.log** file in the LRS system from D:\\Tracing\\LRSAdminLogs\\, and then send it to your LRS support contact.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

