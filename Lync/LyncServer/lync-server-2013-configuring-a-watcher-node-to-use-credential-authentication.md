---
title: 'Lync Server 2013: Настройка узла-наблюдателя для использования проверки подлинности с помощью учетных данных'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ee0d5a07ebd04e6eec585c79eb13b9be7fe98a6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199512"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a><span data-ttu-id="0604e-102">Настройка узла-наблюдателя для использования проверки подлинности с помощью учетных данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0604e-102">Configuring a watcher node to use credential authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0604e-103">_**Последнее изменение темы:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="0604e-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="0604e-p101">Если компьютер узла-наблюдателя находится за пределами сети периметра, то для выполнения искусственных транзакций нужно выполнить немного иную процедуру его настройки. В частности, не следует создавать пул доверенных приложений и доверенное приложение, но нужно установить сертификат, позволяющий узлу-наблюдателю отправлять оповещения на компьютер в пределах сети периметра. Это означает, что нужно выполнить две отдельных задачи:</span><span class="sxs-lookup"><span data-stu-id="0604e-p101">If your watcher node computer lies outside the perimeter network, then you must follow a slightly different procedure in order to configure that watcher node to run synthetic transactions. Specifically, you should not create a trusted application pool and a trusted application, and you must install a certificate that enables the watcher node to send alerts to a computer inside the perimeter network. This means that you will need to complete two separate tasks:</span></span>

  - <span data-ttu-id="0604e-107">обновить членство в группе локальных администраторов RTC компьютера, имеющих право только на чтение;</span><span class="sxs-lookup"><span data-stu-id="0604e-107">Update the membership in the computer's RTC Local Read-only Administrators Group</span></span>

  - <span data-ttu-id="0604e-108">установить файлы конфигурации узла-наблюдателя;</span><span class="sxs-lookup"><span data-stu-id="0604e-108">Install the watcher node configuration files</span></span>

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a><span data-ttu-id="0604e-109">Обновление членства в группе локальных администраторов RTC, имеющих право только на чтение</span><span class="sxs-lookup"><span data-stu-id="0604e-109">Updating Membership in the RTC Local Read-Only Administrators Group</span></span>

<span data-ttu-id="0604e-p102">Если узел-наблюдатель находится за пределами сети периметра, нужно добавить учетную запись сетевой службы в группу локальных администраторов RTC, с правами только на чтение, на компьютере узла-наблюдателя. Для этого на узле-наблюдателе выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0604e-p102">If your watcher node lies outside the perimeter network, you must add the Network Service account to the RTC Local Read-only Administrators group on the watcher node computer. To do this, complete the following procedure on the watcher node:</span></span>

1.  <span data-ttu-id="0604e-112">В меню **Пуск** щелкните правой кнопкой мыши пункт **Компьютер** и выберите пункт **Управление**.</span><span class="sxs-lookup"><span data-stu-id="0604e-112">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>

2.  <span data-ttu-id="0604e-113">В диспетчере серверов разверните узел **Конфигурация**, узел **Локальные пользователи и группы** и щелкните элемент **Группы**.</span><span class="sxs-lookup"><span data-stu-id="0604e-113">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="0604e-114">В области "Группы" дважды щелкните элемент **Локальные администраторы RTC с правом только на чтение**.</span><span class="sxs-lookup"><span data-stu-id="0604e-114">In the Groups pane, double-click **RTC Local Read-only Administrators**.</span></span>

4.  <span data-ttu-id="0604e-115">В диалоговом окне **Локальные администраторы с правами только на чтение RTC** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="0604e-115">In the **RTC Local Read-only Administrators Properties** dialog box, click **Add**.</span></span>

5.  <span data-ttu-id="0604e-116">В диалоговом окне **Выбор пользователей, компьютеров, учетных записей служб или групп** щелкните **Расположения**.</span><span class="sxs-lookup"><span data-stu-id="0604e-116">In the **Select Users, Computers, Service Accounts, or Groups** dialog box, click **Locations**.</span></span>

6.  <span data-ttu-id="0604e-117">В диалоговом окне **Расположения** выберите имя компьютера узла-наблюдателя и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0604e-117">In the **Locations** dialog box, select the name of the watcher node computer, and then click **OK**.</span></span>

7.  <span data-ttu-id="0604e-118">В поле **Введите имена выбираемых объектов** введите **Сетевая служба** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0604e-118">In the **Enter object names to select** box, type **Network Service**, and then click **OK**.</span></span>

8.  <span data-ttu-id="0604e-119">В диалоговом окне **Свойства локальных администраторов RTC с правом только на чтение** нажмите кнопку **ОК** и закройте **Диспетчер серверов**.</span><span class="sxs-lookup"><span data-stu-id="0604e-119">In the **RTC Local Read-only Administrators Properties** dialog box, click **OK**, and then close **Server Manager**.</span></span>

<span data-ttu-id="0604e-120">Перезапустите компьютер узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="0604e-120">Restart the watcher node computer.</span></span>

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a><span data-ttu-id="0604e-121">Установка файлов конфигурации узла-наблюдателя</span><span class="sxs-lookup"><span data-stu-id="0604e-121">Installing the Watcher Node Configuration Files</span></span>

<span data-ttu-id="0604e-122">После перезапуска компьютера узла-наблюдателя нужно запустить файл Watchernode.msi.</span><span class="sxs-lookup"><span data-stu-id="0604e-122">After the watcher node computer has restarted, your next step is to run the file Watchernode.msi.</span></span> <span data-ttu-id="0604e-123">Чтобы запустить этот файл, откройте командную консоль Lync Server 2013, щелкнув **Пуск**, **все программы**, **Lync Server 2013**и выбрав **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="0604e-123">To run this file, open the Lync Server 2013 Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server 2013**, and then clicking **Lync Server Management Shell**.</span></span> <span data-ttu-id="0604e-124">В командной консоли Lync Server введите следующую команду и нажмите клавишу ВВОД (укажите фактический путь к копии Watchernode. msi):</span><span class="sxs-lookup"><span data-stu-id="0604e-124">In the Lync Server Management Shell, type the following command and then press ENTER (be sure and specify the actual path to your copy of Watchernode.msi):</span></span>

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> <span data-ttu-id="0604e-p104">Как указывалось выше, файл Watchernode.msi также можно запустить из окна командной строки. Чтобы открыть это окно, в меню <STRONG>Пуск</STRONG> щелкните правой кнопкой мыши пункт <STRONG>Командная строка</STRONG> и выберите команду <STRONG>Запуск от имени администратора</STRONG>. Когда откроется окно командной строки, введите в нем команду, описанную ранее.</span><span class="sxs-lookup"><span data-stu-id="0604e-p104">As noted previously, Watchernode.msi can also be run from a command window. To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>. When the command window opens, type the same command as shown earlier.</span></span>



</div>

<span data-ttu-id="0604e-128">Режим согласования используется в том случае, если узел-наблюдатель невозможно настроить как пул доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="0604e-128">The Negotiate mode is used any time the watcher node cannot be set up as a trusted application pool.</span></span> <span data-ttu-id="0604e-129">В этом режиме администраторы должны осуществлять управление паролями тестовых пользователей на узле-наблюдателе.</span><span class="sxs-lookup"><span data-stu-id="0604e-129">In this mode, administrators will need to manage test user passwords on the watcher node.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

