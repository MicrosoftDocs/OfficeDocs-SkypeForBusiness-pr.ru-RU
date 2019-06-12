---
title: 'Lync Server 2013: Использование веб-портала администрирования системы комнат Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2369cdde9d14275fddf007b5e073c748ce5a8906
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="eccac-102">Использование веб-портала администрирования системы комнат Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eccac-102">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eccac-103">_**Тема последнего изменения:** 2014-11-10_</span><span class="sxs-lookup"><span data-stu-id="eccac-103">_**Topic Last Modified:** 2014-11-10_</span></span>

<span data-ttu-id="eccac-104">После развертывания ЛРС на сервере вы можете проверить состояние всех комнат ЛРС, войдя на веб-портал ЛРС администрирования из браузера.</span><span class="sxs-lookup"><span data-stu-id="eccac-104">After you deploy LRS on the server, you can check the status of all LRS rooms by signing into the LRS Administrative Web Portal from a browser.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="eccac-105">Вход</span><span class="sxs-lookup"><span data-stu-id="eccac-105">Sign in</span></span>

1.  <span data-ttu-id="eccac-106">Перейдите по следующему URL-адресу:</span><span class="sxs-lookup"><span data-stu-id="eccac-106">Browse to the following URL:</span></span>
    
    <span data-ttu-id="eccac-107">https://\<Fe-Server\>/ЛРС</span><span class="sxs-lookup"><span data-stu-id="eccac-107">https://\<fe-server\>/lrs</span></span>

2.  <span data-ttu-id="eccac-108">Введите учетные данные учетной записи Лрссуппорт или учетной записи, добавленной в группу безопасности Лрссуппортадминграуп.</span><span class="sxs-lookup"><span data-stu-id="eccac-108">Enter the credentials for the LRSSupport account or an account that has been added to the LRSSupportAdminGroup security group.</span></span>

<span data-ttu-id="eccac-109">![Экран входа в систему на портале администратора системы Lync в комнате] (images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Экран входа в систему на портале администратора системы Lync в комнате")</span><span class="sxs-lookup"><span data-stu-id="eccac-109">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a><span data-ttu-id="eccac-110">Общая страница веб-портала ЛРС администрирования</span><span class="sxs-lookup"><span data-stu-id="eccac-110">LRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="eccac-111">На странице Сводка представлены следующие сведения о всех ЛРС комнатах, развернутых на сервере.</span><span class="sxs-lookup"><span data-stu-id="eccac-111">The summary page provides the following information for all of the LRS rooms deployed on the server:</span></span>

  - <span data-ttu-id="eccac-112">**Пометьте**   настраиваемое имя, которое администратор предоставляет в комнате.</span><span class="sxs-lookup"><span data-stu-id="eccac-112">**Tag**   The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="eccac-113">Тег можно задать на портале, щелкнув имя конференц-зала.</span><span class="sxs-lookup"><span data-stu-id="eccac-113">The Tag can be set in the portal by clicking on the room name.</span></span>

  - <span data-ttu-id="eccac-114">\*\*\*\* Состояние работоспособности комнаты, которая является производной от сводного состояния работоспособности комнаты, которая отображается в разделе работоспособность на странице Параметры комнаты.   </span><span class="sxs-lookup"><span data-stu-id="eccac-114">**Health**   The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

  - <span data-ttu-id="eccac-115">**Следующее собрание**   . Дата и время запланированного следующего собрания.</span><span class="sxs-lookup"><span data-stu-id="eccac-115">**Next Meeting**   The date and time the next meeting is scheduled.</span></span>

  - <span data-ttu-id="eccac-116">**Версия ЛРС, производитель, модель**   эти значения предварительно заданы в ЛРС.</span><span class="sxs-lookup"><span data-stu-id="eccac-116">**LRS Version, Manufacturer, Model**   These values are preset in LRS.</span></span> <span data-ttu-id="eccac-117">В зависимости от производителя данные поля могут оставаться пустыми.</span><span class="sxs-lookup"><span data-stu-id="eccac-117">Depending on the manufacturer, these fields might be left blank.</span></span>

  - <span data-ttu-id="eccac-118">**Последнее обновление**   показывает время последнего обновления веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="eccac-118">**Last Refresh**   Displays the last time the webpage was refreshed.</span></span>

<span data-ttu-id="eccac-119">![Представление сводки на портале администратора системы Lync в комнате] (images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Представление сводки на портале администратора системы Lync в комнате")</span><span class="sxs-lookup"><span data-stu-id="eccac-119">![Lync Room System Admin Portal Summary View](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync Room System Admin Portal Summary View")</span></span>

</div>

<div>

## <a name="lrs-room-information"></a><span data-ttu-id="eccac-120">Информация о ЛРС помещении</span><span class="sxs-lookup"><span data-stu-id="eccac-120">LRS Room Information</span></span>

<span data-ttu-id="eccac-121">Раздел "сведения о комнате" на портале позволяет просматривать и настраивать отдельные комнаты ЛРС.</span><span class="sxs-lookup"><span data-stu-id="eccac-121">The Room Info section of the portal allows you to view and configure individual LRS rooms.</span></span> <span data-ttu-id="eccac-122">В нем содержатся четыре раздела: параметры, сведения, устранение неполадок и исправность.</span><span class="sxs-lookup"><span data-stu-id="eccac-122">It contains four sections: Settings, Details, Troubleshooting, and Health.</span></span>

<div>

## <a name="settings"></a><span data-ttu-id="eccac-123">Параметры</span><span class="sxs-lookup"><span data-stu-id="eccac-123">Settings</span></span>

<span data-ttu-id="eccac-124">В разделе "Параметры" для выбранного конференц-зала можно задать пароль, тег конференц-зала и уровни громкости по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="eccac-124">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="eccac-125">Если вы настроили эти параметры, изменения реплицируются только после перезапуска консоли ЛРС.</span><span class="sxs-lookup"><span data-stu-id="eccac-125">If you configure these settings, the changes are replicated only after you restart the LRS console.</span></span> <span data-ttu-id="eccac-126">Вы увидите только параметры обновлений системы для комнатных систем Lync, которые имеют версию 15,12 и более поздние версии.</span><span class="sxs-lookup"><span data-stu-id="eccac-126">You will only see System Updates settings for Lync Room Systems that are version 15.12 and later.</span></span>

<span data-ttu-id="eccac-127">![Параметры комнаты на портале администратора системы Lync в комнате] (images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Параметры комнаты на портале администратора системы Lync в комнате")</span><span class="sxs-lookup"><span data-stu-id="eccac-127">![Lync Room System Admin Portal Room Settings](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync Room System Admin Portal Room Settings")</span></span>

</div>

<div>

## <a name="details"></a><span data-ttu-id="eccac-128">Подробности</span><span class="sxs-lookup"><span data-stu-id="eccac-128">Details</span></span>

<span data-ttu-id="eccac-129">В разделе "сведения" представлена сводка по параметрам ЛРС комнаты, которая доступна только для чтения, в том числе: время последнего обновления; следующее собрание; Последние обновления, Обслуживание и калибровка; Параметры динамика, микрофона и звонка по умолчанию; Версия УНИВЕРСАЛЬНЫЙ КОД РЕСУРСА (URI) SIP; Количество экранов и подробные сведения о каждом экране; состояние и активность.</span><span class="sxs-lookup"><span data-stu-id="eccac-129">The Details section provides a read-only summary of the LRS room’s settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

<span data-ttu-id="eccac-130">![Представление сведений о портале администрирования системы Lync в комнате] (images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Представление сведений о портале администрирования системы Lync в комнате")</span><span class="sxs-lookup"><span data-stu-id="eccac-130">![Lync Room System Admin Portal Detail View](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync Room System Admin Portal Detail View")</span></span>

</div>

<div>

## <a name="troubleshooting"></a><span data-ttu-id="eccac-131">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="eccac-131">Troubleshooting</span></span>

<span data-ttu-id="eccac-132">Раздел "Поиск и устранение неполадок" можно использовать для удаленного сбора журналов и их сохранения в указанном месте.</span><span class="sxs-lookup"><span data-stu-id="eccac-132">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="eccac-133">Вы также можете перезапустить консоль ЛРС (пользовательский интерфейс ЛРС) или перезапустить всю систему.</span><span class="sxs-lookup"><span data-stu-id="eccac-133">You can also restart the LRS console (LRS user interface) or restart the entire system.</span></span> <span data-ttu-id="eccac-134">Чтобы собрать журналы, укажите путь к папке в указанном формате и убедитесь, что в папке есть разрешения на запись, предоставленные учетной записи компьютера ЛРС.</span><span class="sxs-lookup"><span data-stu-id="eccac-134">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the LRS machine account.</span></span> <span data-ttu-id="eccac-135">Если журнал имеет слишком большой размер, процесс сбора журналов может занять до пяти минут.</span><span class="sxs-lookup"><span data-stu-id="eccac-135">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="eccac-136">Для просмотра актуального состояния обновите страницу.</span><span class="sxs-lookup"><span data-stu-id="eccac-136">Refreshing the page will give you the latest status.</span></span>

<span data-ttu-id="eccac-137">![Ведение журнала на комнате администратора системы Lync в комнате] (images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Ведение журнала на комнате администратора системы Lync в комнате")</span><span class="sxs-lookup"><span data-stu-id="eccac-137">![Lync Room System Admin Portal Room Logging](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync Room System Admin Portal Room Logging")</span></span>

</div>

<div>

## <a name="health"></a><span data-ttu-id="eccac-138">Работоспособность</span><span class="sxs-lookup"><span data-stu-id="eccac-138">Health</span></span>

<span data-ttu-id="eccac-139">Раздел Health — наглядный индикатор работоспособности соединения с сервером Lync, звуковым устройством, видеоустройства, состоянием устойчивости и устройством экрана.</span><span class="sxs-lookup"><span data-stu-id="eccac-139">The Health section gives a visual indication of the health of the Lync Server connection, audio device, video device, resiliency state, and screen device.</span></span>

<span data-ttu-id="eccac-140">![Работоспособность комнаты портала администратора для системы Lync в комнате] (images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Работоспособность комнаты портала администратора для системы Lync в комнате")</span><span class="sxs-lookup"><span data-stu-id="eccac-140">![Lync Room System Admin Portal Room Health](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync Room System Admin Portal Room Health")</span></span>

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="eccac-141">Дополнительные примечания о веб-портале администрирования</span><span class="sxs-lookup"><span data-stu-id="eccac-141">Additional Notes about the Administrative Web Portal</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="eccac-142">Изменения параметров вступают в силу только после перезапуска системы ЛРС.</span><span class="sxs-lookup"><span data-stu-id="eccac-142">Setting changes are applied only after the LRS system is restarted.</span></span></P>
> <LI>
> <P><span data-ttu-id="eccac-143">Если истек срок действия пароля учетной записи LRSApp, просмотреть состояние конференц-залов невозможно.</span><span class="sxs-lookup"><span data-stu-id="eccac-143">If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="eccac-144">Настройте пароль учетной записи Лрсаппусер таким образом, чтобы он никогда не истекал, или обновите пароль, если он приближается к истечении срока действия.</span><span class="sxs-lookup"><span data-stu-id="eccac-144">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it’s near expiration.</span></span></P>
> <LI>
> <P><span data-ttu-id="eccac-145">Веб-портал ЛРС администрирования поддерживается только для локальных развертываний.</span><span class="sxs-lookup"><span data-stu-id="eccac-145">The LRS administrative web portal is supported for on-premises deployments only.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="eccac-146">Ответы на часто задаваемые вопросы</span><span class="sxs-lookup"><span data-stu-id="eccac-146">Frequently Asked Questions</span></span>

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="eccac-147">Почему не удается войти на веб-портал администрирования?</span><span class="sxs-lookup"><span data-stu-id="eccac-147">Why can’t I sign in to the administrative web portal?</span></span>

  - <span data-ttu-id="eccac-148">После открытия https://localhost/lrsстраницы входа вы сможете увидеть ее, но при вводе учетных данных вы не сможете войти в нее.</span><span class="sxs-lookup"><span data-stu-id="eccac-148">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="eccac-149">В этом случае вы должны открыть https://FQDNofFEserver/lrs для входа на веб-портал администрирования.</span><span class="sxs-lookup"><span data-stu-id="eccac-149">In this case, you must open https://FQDNofFEserver/lrs to sign in to the administrative web portal.</span></span>

  - <span data-ttu-id="eccac-150">Если компьютер, с которого осуществляется доступ к веб-порталу администрирования, находится в Рабочей группе, "http://" работать не будет.</span><span class="sxs-lookup"><span data-stu-id="eccac-150">If the machine from which you are accessing the administrative web portal is in a workgroup, "http://" will not work.</span></span> <span data-ttu-id="eccac-151">Вместо этого используйте "HTTPS".</span><span class="sxs-lookup"><span data-stu-id="eccac-151">Use "https" instead.</span></span>

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="eccac-152">Почему я не вижу ЛРС на веб-портале администрирования?</span><span class="sxs-lookup"><span data-stu-id="eccac-152">Why can’t I see LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="eccac-153">Убедитесь в том, что у вас есть учетные записи ЛРС в развертывании и они созданы в соответствии с рекомендациями по развертыванию веб-портала ЛРС администратора.</span><span class="sxs-lookup"><span data-stu-id="eccac-153">Make sure you have LRS accounts in your deployment and that they are created according to the LRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="eccac-154">Убедитесь в том, что учетные записи ЛРС предоставлены с помощью команды Enable-Ксмитингрум, а не Enable-CsUser на сервере Lync.</span><span class="sxs-lookup"><span data-stu-id="eccac-154">Make sure the LRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Lync server.</span></span>

  - <span data-ttu-id="eccac-155">Если вы создали учетные записи ЛРС и не видите учетные записи на веб-портале администрирования, соберите журналы сервера с помощью средства ведения журнала на Lync Server с выбранным компонентом **митингпортал** , а затем отправьте их в контакт службы поддержки ЛРС.</span><span class="sxs-lookup"><span data-stu-id="eccac-155">If you have created LRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Lync Server Logging tool with the **MeetingPortal** component selected, and then send them to your LRS support contact.</span></span>

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="eccac-156">Почему я не вижу состояние ЛРС на веб-портале администрирования?</span><span class="sxs-lookup"><span data-stu-id="eccac-156">Why can’t I see the status of LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="eccac-157">Убедитесь, что для учетной записи пользователя LRSApp включена поддержка SIP.</span><span class="sxs-lookup"><span data-stu-id="eccac-157">Make sure that the LRSApp user account is SIP-enabled.</span></span>

  - <span data-ttu-id="eccac-158">Если у вас по-прежнему возникают проблемы, выполните сбор файла **Trace. log** в системе ЛРС с D\\:\\Tracing\\лрсадминлогс, а затем отправьте его в контакт службы поддержки ЛРС.</span><span class="sxs-lookup"><span data-stu-id="eccac-158">If you are still having issues, collect the **Trace.log** file in the LRS system from D:\\Tracing\\LRSAdminLogs\\, and then send it to your LRS support contact.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

