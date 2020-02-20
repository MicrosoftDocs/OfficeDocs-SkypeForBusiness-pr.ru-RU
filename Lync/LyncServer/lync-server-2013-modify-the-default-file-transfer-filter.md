---
title: 'Lync Server 2013: изменение фильтра передачи файлов по умолчанию'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 998e14fc0f30b29d0477dc1363f03a84a7ffe775
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a><span data-ttu-id="50efa-102">Изменение фильтра передачи файлов по умолчанию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50efa-102">Modify the default file transfer filter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50efa-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="50efa-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="50efa-104">Lync Server 2013 предоставляет глобальный фильтр передачи файлов, который блокирует определенные типы файлов во время выполнения следующих действий с файлами в развертывании Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="50efa-104">Lync Server 2013 provides a global file transfer filter that blocks specific types of files during the following file-related activities within your Lync Server 2013 deployment:</span></span>

  - <span data-ttu-id="50efa-105">Запросы на передачу файлов во время бесед с обменом мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="50efa-105">File transfer requests during instant messaging (IM) conversations</span></span>

  - <span data-ttu-id="50efa-106">Отправки и загрузки файлов во время использования функции выдачи в клиенте Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="50efa-106">File uploads and downloads while using the handout feature in the Office Live Meeting 2007 client</span></span>

  - <span data-ttu-id="50efa-107">Воспроизведение мультимедиа во время конференций</span><span class="sxs-lookup"><span data-stu-id="50efa-107">Multimedia playback during conferences</span></span>

<span data-ttu-id="50efa-108">В зависимости от типов файлов, которые необходимо заблокировать или разрешить, можно использовать панель управления Lync Server для изменения глобального фильтра.</span><span class="sxs-lookup"><span data-stu-id="50efa-108">Depending on the types of files you want to block or allow, you can use Lync Server Control Panel to modify the global filter.</span></span> <span data-ttu-id="50efa-109">Подробные сведения о фильтрации передачи файлов приведены [в разделе Настройка передачи файлов и фильтрации URL-адресов для обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="50efa-109">For details about file transfer filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a><span data-ttu-id="50efa-110">Изменение фильтра передачи файлов по умолчанию</span><span class="sxs-lookup"><span data-stu-id="50efa-110">To modify the default file transfer filter</span></span>

1.  <span data-ttu-id="50efa-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="50efa-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="50efa-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="50efa-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="50efa-113">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="50efa-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="50efa-114">В левой области навигации щелкните пункт **Мгновенные сообщения и присутствие**, а затем **Фильтр файлов**.</span><span class="sxs-lookup"><span data-stu-id="50efa-114">In the left navigation bar, click **IM and Presence** and then click **File Filter**.</span></span>

4.  <span data-ttu-id="50efa-115">На странице **File Filter** (Фильтр файлов) дважды щелкните фильтр **Global** (Глобальный).</span><span class="sxs-lookup"><span data-stu-id="50efa-115">On the **File Filter** page, double-click the **Global** filter.</span></span>

5.  <span data-ttu-id="50efa-116">В окне **Edit File Filter** (Изменение фильтра файлов) установите флажок **Enable file filter** (Включить фильтр файлов).</span><span class="sxs-lookup"><span data-stu-id="50efa-116">In **Edit File Filter**, select the **Enable file filter** check box.</span></span>

6.  <span data-ttu-id="50efa-117">В раскрывающемся списке **Передача файлов** выберите пункт **Блокировать все** или **Block specific file types** (Блокировать определенные типы файлов).</span><span class="sxs-lookup"><span data-stu-id="50efa-117">In the **File transfer** drop-down list box, click **Block All** or **Block specific file types**.</span></span>

7.  <span data-ttu-id="50efa-118">При выборе варианта **Блокировать все** перейдите к действию 9.</span><span class="sxs-lookup"><span data-stu-id="50efa-118">If you clicked **Block All**, skip to step 9.</span></span>

8.  <span data-ttu-id="50efa-119">При выборе варианта **Блокировать определенные типы файлов** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="50efa-119">If you clicked **Block specific file types**, do the following:</span></span>
    
    1.  <span data-ttu-id="50efa-120">Щелкните **Выбрать**, чтобы изменить список блокируемых расширений файлов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="50efa-120">Click **Select** to modify the default list of file type extensions that you want to block.</span></span>
    
    2.  <span data-ttu-id="50efa-121">В окне **Select File Type** (Выбор типа файла) выберите типы файлов, которые требуется блокировать или разрешить, добавив или удалив их расширения из категорий в разделе **File type extensions** (Расширения типов файлов).</span><span class="sxs-lookup"><span data-stu-id="50efa-121">In **Select File Type**, select the file types that you want to block or allow by adding or removing their extensions from the categories under **File type extensions**.</span></span>
    
    3.  <span data-ttu-id="50efa-122">Если расширения типов файлов, которые необходимо заблокировать, не отображаются, введите расширение в текстовое поле **Add file type extensions to the list** (Добавить расширения типов файлов в список), а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="50efa-122">If you do not see the extension for a file type that you want to block, type the extension in the text box under **Add file type extensions to the list**, and then click **Add**.</span></span>
    
    4.  <span data-ttu-id="50efa-123">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="50efa-123">Click **OK**.</span></span>

9.  <span data-ttu-id="50efa-124">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="50efa-124">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="50efa-125">См. также</span><span class="sxs-lookup"><span data-stu-id="50efa-125">See Also</span></span>


[<span data-ttu-id="50efa-126">Настройка передачи файлов и фильтрации URL-адресов для обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50efa-126">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="50efa-127">Создание нового фильтра передачи файлов в Lync Server 2013 для определенного сайта</span><span class="sxs-lookup"><span data-stu-id="50efa-127">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="50efa-128">Создание нового фильтра URL-адресов в Lync Server 2013 для обработки гиперссылок в текстовых беседах</span><span class="sxs-lookup"><span data-stu-id="50efa-128">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[<span data-ttu-id="50efa-129">Изменение фильтра URL-адресов по умолчанию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50efa-129">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

