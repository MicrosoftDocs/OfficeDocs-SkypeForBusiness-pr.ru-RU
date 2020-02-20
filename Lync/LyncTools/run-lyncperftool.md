---
title: Запуск Линкперфтул
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5325a3dab058132dfe6bbf8558ebe771450f36ac
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-lyncperftool"></a><span data-ttu-id="dba25-102">Запуск Линкперфтул</span><span class="sxs-lookup"><span data-stu-id="dba25-102">Run LyncPerfTool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dba25-103">_**Последнее изменение темы:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="dba25-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="dba25-104">Перед запуском средства нагрузки и производительности Lync Server 2013 (Линкперфтул. exe) необходимо создать пользователей, контакты и сценарии.</span><span class="sxs-lookup"><span data-stu-id="dba25-104">Before running the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe), you must create users, contacts, and scenarios.</span></span> <span data-ttu-id="dba25-105">Сведения об использовании средств для выполнения этих действий приведены в статье [Создание пользователей и контактов](create-users-and-contacts.md) и [Настройка профиля пользователя](configure-user-profile.md).</span><span class="sxs-lookup"><span data-stu-id="dba25-105">For details about using the tools to perform these actions, see [Create Users and Contacts](create-users-and-contacts.md) and [Configure User Profile](configure-user-profile.md).</span></span> <span data-ttu-id="dba25-106">При запуске этих средств также будет создан файл, который будет запускать Линкперфтул. exe в составе пакетного файла с необходимыми параметрами.</span><span class="sxs-lookup"><span data-stu-id="dba25-106">Running these tools will also generate a file that will run LyncPerfTool.exe as part of a batch file with the required parameters included.</span></span>

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="dba25-107">Запуск средства нагрузочного тестирования и производительности Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dba25-107">Running the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="dba25-108">Средство Усерпрофилеженератор. exe создает пакетный файл, который позволяет запустить Линкперфтул. exe, зарегистрировав счетчики производительности Линкперфтул и загрузив XML-файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="dba25-108">The UserProfileGenerator.exe tool creates a batch file that enables you to run LyncPerfTool.exe by registering the LyncPerfTool performance counters and loading the XML configuration file.</span></span> <span data-ttu-id="dba25-109">Пакетный файл запускает один экземпляр Линкперфтул. exe для каждого файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="dba25-109">The batch file runs one instance of LyncPerfTool.exe per configuration file.</span></span> <span data-ttu-id="dba25-110">Чтобы запустить пакетный файл, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="dba25-110">To run the batch file, do the following:</span></span>

1.  <span data-ttu-id="dba25-111">Скопируйте папку, содержащую папки и файлы конфигурации, в каталог, содержащий Линкстресстул. exe на каждом клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="dba25-111">Copy the folder that contains the configuration folders and files to the directory that contains LyncStressTool.exe on each client computer.</span></span> <span data-ttu-id="dba25-112">(Например, если вы создали файлы конфигурации в папке с именем 1,28\_13.16.16, скопируйте эту папку в папку, содержащую линкперфтул. exe на каждом клиенте.)</span><span class="sxs-lookup"><span data-stu-id="dba25-112">(For example, if you generated the configuration files in the folder named 1.28\_13.16.16, copy that folder to the folder that contains LyncPerfTool.exe on each client.)</span></span>

2.  <span data-ttu-id="dba25-113">Перейдите к папке клиента с соответствующим номером и запустите пакетный сценарий Рунклиент.</span><span class="sxs-lookup"><span data-stu-id="dba25-113">Navigate to the appropriately numbered client folder and run the RunClient batch script.</span></span> <span data-ttu-id="dba25-114">Можно просто дважды щелкнуть пакетный файл в проводнике Windows, который будет выполнять все файлы конфигурации для этого номера клиента.</span><span class="sxs-lookup"><span data-stu-id="dba25-114">You can simply double-click the batch file in Windows Explorer and it will run all of the configuration files for that client number.</span></span> <span data-ttu-id="dba25-115">Вы также можете запустить скрипт из соответствующей клиентской папки с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="dba25-115">You can also run the script from the appropriate client folder by using the following syntax:</span></span>

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
<span data-ttu-id="dba25-116">Чтобы запустить Линкперфтул. exe напрямую, откройте командную строку и введите в командной строке следующую команду (при первом запуске обязательно Зарегистрируйте счетчики производительности regsvr32/i/n/s Линкперфтулперф. dll, как показано в заметке далее в этом разделе): Линкперфтул. exe/file:\<configXML\></span><span class="sxs-lookup"><span data-stu-id="dba25-116">To run LyncPerfTool.exe directly, open a command prompt, and then type the following command at the command line (when doing this for the first time, be sure to register the performance counters regsvr32 /i /n /s LyncPerfToolPerf.dll, as show in the note later in this topic):LyncPerfTool.exe /file:\<configXML\></span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
<span data-ttu-id="dba25-117">Чтобы средство отображало значения в файле конфигурации, включите в предыдущую команду параметр/дисплайфиле, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="dba25-117">To have the tool display the values in the configuration file, include the /displayfile parameter on the preceding command, like this:</span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
<span data-ttu-id="dba25-118">Чтобы завершить процесс, нажмите клавиши CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="dba25-118">To end the process, press Ctrl+C.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dba25-119">Перед запуском Линкперфтул напрямую необходимо зарегистрировать счетчики производительности.</span><span class="sxs-lookup"><span data-stu-id="dba25-119">Before running LyncPerfTool directly, you must register the performance counters.</span></span> <span data-ttu-id="dba25-120">Введите следующую команду, чтобы зарегистрировать счетчики производительности:</span><span class="sxs-lookup"><span data-stu-id="dba25-120">Enter the following command to register performance counters:</span></span>



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> <span data-ttu-id="dba25-121">Каждый запущенный экземпляр Линкперфтул. exe сразу же начинает вход в систему пользователей, как правило, на частоте одного пользователя в секунду.</span><span class="sxs-lookup"><span data-stu-id="dba25-121">Every instance of LyncPerfTool.exe that you start will immediately start signing in users, usually at a rate of one user per second.</span></span> <span data-ttu-id="dba25-122">Пиковая частота входа пользователей в пул составляет около 12 в секунду.</span><span class="sxs-lookup"><span data-stu-id="dba25-122">The peak user sign-in rate for the pool is about 12 per second.</span></span> <span data-ttu-id="dba25-123">Это означает, что не следует запускать более 12 экземпляров Линкперфтул одновременно, а пользователи по-прежнему подписываются.</span><span class="sxs-lookup"><span data-stu-id="dba25-123">This means that you should not start more than 12 LyncPerfTool instances at the same time, while the users are still signing in.</span></span> <span data-ttu-id="dba25-124">1000 пользователям потребуется около 20 минут, чтобы выполнять вход по одной в секунду.</span><span class="sxs-lookup"><span data-stu-id="dba25-124">1000 users will take about 20 minutes to fully sign in, at one per second.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dba25-125">См. также</span><span class="sxs-lookup"><span data-stu-id="dba25-125">See Also</span></span>


[<span data-ttu-id="dba25-126">Создание пользователей и контактов</span><span class="sxs-lookup"><span data-stu-id="dba25-126">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
[<span data-ttu-id="dba25-127">Настройка профиля пользователя</span><span class="sxs-lookup"><span data-stu-id="dba25-127">Configure User Profile</span></span>](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

