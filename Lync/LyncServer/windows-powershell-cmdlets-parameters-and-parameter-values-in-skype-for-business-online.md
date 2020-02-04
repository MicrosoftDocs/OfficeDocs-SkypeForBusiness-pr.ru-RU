---
title: Командлеты, параметры и значения параметров Windows PowerShell в Skype для бизнеса Online
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2d607b4a7e7cf87a08082a820f3b3a216621de3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a><span data-ttu-id="7b5a9-102">Командлеты, параметры и значения параметров Windows PowerShell в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="7b5a9-102">Windows PowerShell cmdlets, parameters, and parameter values in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b5a9-103">_**Тема последнего изменения:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="7b5a9-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="7b5a9-104">Если вы знакомы с окном команд, которое находится во всех версиях Windows (или если вы знакомы с MS-DOS), вы получите головной старт, когда научитесь использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-104">If you are familiar with the command window found in all versions of Windows (or if you are familiar with MS-DOS), then you’ll have a head start when it comes to learning how to use Windows PowerShell.</span></span> <span data-ttu-id="7b5a9-105">В окне команд введите команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-105">In the command window, you type a command and press ENTER.</span></span> <span data-ttu-id="7b5a9-106">В ответ компьютер запускает команду или исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-106">In response, the computer runs a command or an executable file.</span></span> <span data-ttu-id="7b5a9-107">Например, чтобы получить сведения обо всех файлах и папках в текущем каталоге, введите эту команду в командной строке и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-107">For example, to return information about all the files and folders in the current directory, you’d type this command at the command prompt and then press ENTER:</span></span>

    dir

<span data-ttu-id="7b5a9-108">В свою очередь вы получаете сведения обо всех файлах и папках в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="7b5a9-108">In turn, you get back information about all the files and folders in the current directory:</span></span>

``` 
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/13/2013  02:53 PM                 117   pldok.log
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/21/2013  03:37 PM            207   setup.doc
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

<span data-ttu-id="7b5a9-109">Это один из примеров результата, когда вы вводите только имя команды или исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-109">That’s one example of a result when you do type only the name of a command or an executable file.</span></span> <span data-ttu-id="7b5a9-110">Однако многие из команд, выполняемых в окне команд, также поддерживают *аргументы*.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-110">However, many of the commands that are run from within the command window also accept *arguments*.</span></span> <span data-ttu-id="7b5a9-111">Аргументы — это дополнительные фрагменты данных, которые передаются команде, изменяя поведение команды.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-111">Arguments are additional pieces of information that are passed to the command, which modify the behavior of the command.</span></span> <span data-ttu-id="7b5a9-112">Например, если вы хотите просмотреть имена файлов и папок в текущем каталоге, не другие сведения, такие как размер файла или папки, а также дату и время создания папки или папки.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-112">For example, if you only wanted to see the names of the files and folder in the current directory—no other information, such as the size of the file or folder, or the date and time that the folder or folder was created.</span></span> <span data-ttu-id="7b5a9-113">В этом случае при запуске команды dir нужно добавить аргумент **/b** .</span><span class="sxs-lookup"><span data-stu-id="7b5a9-113">In this case, you’d append the **/b** argument when running the dir command:</span></span>

    dir /b

<span data-ttu-id="7b5a9-114">После включения аргумента **/b** команда **dir** выводит только имена папок и файлов, найденных в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-114">When you include the **/b** argument, the **dir** command reports back only the names of the folders and files found in the current directory:</span></span>

    Deploy
    Intel
    PerfLogs
    Program Files
    Program Files (x86)
    Users
    Windows
    pldok.log
    RHDSetup.exe
    setup.doc

<span data-ttu-id="7b5a9-115">В предыдущей команде аргумент **/b** — это единственная информация, необходимая для ограничения возвращенных данных именами файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-115">In the preceding command, the **/b** argument is the only information required to limit the returned data to file and folder names.</span></span> <span data-ttu-id="7b5a9-116">Это часто относится к командам командной строки: для изменения поведения команды необходимо всего лишь наличие аргумента.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-116">This is often the case with command-line commands: the mere presence of an argument is all that’s needed to change the command’s behavior.</span></span> <span data-ttu-id="7b5a9-117">(То есть, вы можете добавить аргумент **/b** , чтобы скрыть дополнительные сведения, или аргумент **/b** , чтобы отобразить дополнительные сведения). Однако в других случаях необходимо указать *значение аргумента*.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-117">(That is, you include the **/b** argument to hide additional information, or you exclude the **/b** argument to show the extra information.) At other times, however, you must specify an *argument value*.</span></span> <span data-ttu-id="7b5a9-118">Значение аргумента — это дополнительная информация, передаваемая самим аргументом.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-118">An argument value is additional information passed to the argument itself.</span></span> <span data-ttu-id="7b5a9-119">Например, аргумент **/o** позволяет указать способ сортировки возвращенных данных командой dir.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-119">For instance, the **/o** argument enables you to specify how you would like the dir command to sort the returned data.</span></span> <span data-ttu-id="7b5a9-120">Среди других параметров можно использовать значение аргумента **e** для сортировки по расширению файла или значения аргумента для **сортировки по размеру** файла.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-120">Among other options, you can use the argument value **e** to sort by file extension or the argument value **s** to sort by file size.</span></span> <span data-ttu-id="7b5a9-121">Например, с помощью этой команды возвращенные данные сортируются по расширению файла.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-121">For example, this command sorts the returned data by file extension.</span></span> <span data-ttu-id="7b5a9-122">Обратите внимание на то, как значение аргумента **e** включается сразу после аргумента **/o** :</span><span class="sxs-lookup"><span data-stu-id="7b5a9-122">Note how the argument value **e** is included immediately after the **/o** argument:</span></span>

    dir /oe

<span data-ttu-id="7b5a9-123">При использовании нашей учебной папки возвращенные данные будут выглядеть следующим образом: файлы сортируются в алфавитном порядке по расширению файла.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-123">Using our sample folder, the returned data will look like this, with the files sorted alphabetically by file extension:</span></span>

``` 
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/21/2013  03:37 PM            207   setup.doc
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/13/2013  02:53 PM                 117   pldok.log
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

<span data-ttu-id="7b5a9-124">Или, чтобы помочь вам точно определить, о чем мы говорим.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-124">Or, to help you pinpoint exactly what we are talking about:</span></span>

<span data-ttu-id="7b5a9-125">Настройка.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-125">setup.</span></span> <span data-ttu-id="7b5a9-126">**тов**</span><span class="sxs-lookup"><span data-stu-id="7b5a9-126">**doc**</span></span>  
<span data-ttu-id="7b5a9-127">Рхдсетуп.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-127">RHDSetup.</span></span> <span data-ttu-id="7b5a9-128">**exe**</span><span class="sxs-lookup"><span data-stu-id="7b5a9-128">**exe**</span></span>  
<span data-ttu-id="7b5a9-129">плдок.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-129">pldok.</span></span> <span data-ttu-id="7b5a9-130">**выходе**</span><span class="sxs-lookup"><span data-stu-id="7b5a9-130">**log**</span></span>

<span data-ttu-id="7b5a9-131">Несмотря на то, что Windows PowerShell использует другую терминологию, основной подход к работе с Windows PowerShell — это то же самое, что и окно команд: вы вводите команды, добавляют аргументы и значения аргументов по мере необходимости, а затем нажимаете клавишу ВВОД, чтобы выполнить Эти команды.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-131">Although Windows PowerShell uses different terminology, the basic approach to working with Windows PowerShell is the same as working with the command window: you type commands, you include arguments and argument values as needed, and then you press ENTER to execute those commands.</span></span> <span data-ttu-id="7b5a9-132">Однако в Windows PowerShell используется другая терминология, чем при использовании командной оболочки.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-132">As noted, however, Windows PowerShell does use a different terminology than the command shell uses.</span></span> <span data-ttu-id="7b5a9-133">В Windows PowerShell выполняемые команды известны как *командлеты*.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-133">In Windows PowerShell, the commands you execute are known as *cmdlets*.</span></span> <span data-ttu-id="7b5a9-134">В свою очередь аргументы, передаваемые командлету, называются *параметрами*, и значения, передаваемые параметру, называются *значениями параметров*.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-134">In turn, the arguments passed to a cmdlet are known as *parameters*, and the values passed to a parameter are known as *parameter values*.</span></span>

<span data-ttu-id="7b5a9-135">Предыдущие определения довольно упрощены.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-135">The preceding definitions are somewhat simplified.</span></span> <span data-ttu-id="7b5a9-136">Командлеты — это, по сути, мини-приложения, которые можно запускать только в среде Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-136">Cmdlets are essentially mini-applications that can be run only from within the Windows PowerShell environment.</span></span> <span data-ttu-id="7b5a9-137">Однако вы также можете запускать другие команды и приложения из Windows PowerShell, в том числе в большинстве команд и приложений, которые можно запускать из командного окна.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-137">However, you can also run other commands and applications from within Windows PowerShell, including most of the commands and applications that can be run from a command window.</span></span> <span data-ttu-id="7b5a9-138">Например, если вы хотите запустить блокнот из Windows PowerShell, все, что вам нужно сделать, — это ввести следующую команду и нажать клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-138">For example, if you want to start Notepad from within Windows PowerShell, all you need to do is type the following and press ENTER:</span></span>

    notepad.exe

<span data-ttu-id="7b5a9-139">Однако при управлении Skype для бизнеса Online большинство администраторов будут использовать командлеты Windows PowerShell для выполнения административных задач.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-139">When it comes to managing Skype for Business Online, however, most administrators will rely on Windows PowerShell cmdlets to carry out administrative tasks.</span></span> <span data-ttu-id="7b5a9-140">В каждый момент времени есть и другие команды или приложения, которые можно использовать для управления Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-140">At time, there are very few other types of commands or applications that can be used to manage Skype for Business Online.</span></span> <span data-ttu-id="7b5a9-141">Иногда командлеты Skype для бизнеса Online можно использовать без дополнительных аргументов (как указано в разделе "аргументы" — "Параметры" в Windows PowerShell).</span><span class="sxs-lookup"><span data-stu-id="7b5a9-141">Sometimes the Skype for Business Online cmdlets can be used without any additional arguments (, as noted, arguments are known as parameters in Windows PowerShell).</span></span> <span data-ttu-id="7b5a9-142">Например, следующая команда вызывает командлет [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) без дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-142">For example, the following command calls the [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) cmdlet without any additional parameters.</span></span> <span data-ttu-id="7b5a9-143">Сама по себе она возвращает сведения обо всех пользователях Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="7b5a9-143">By itself, the command returns information about all of your Skype for Business Online users:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="7b5a9-144">Однако большинство командлетов Skype для бизнеса Online также допускают параметры (и значения параметров).</span><span class="sxs-lookup"><span data-stu-id="7b5a9-144">However, most of the Skype for Business Online cmdlets also accept parameters (and parameter values).</span></span> <span data-ttu-id="7b5a9-145">Рассматривайте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7b5a9-145">Consider the following command:</span></span>

    Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"

<span data-ttu-id="7b5a9-146">Эта команда состоит из трех частей:</span><span class="sxs-lookup"><span data-stu-id="7b5a9-146">This command consists of three parts:</span></span>

  - <span data-ttu-id="7b5a9-147">Командлет **Get-CsOnlineUser**.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-147">The cmdlet **Get-CsOnlineUser**.</span></span>

  - <span data-ttu-id="7b5a9-148">Параметр Identity.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-148">The Identity parameter.</span></span> <span data-ttu-id="7b5a9-149">Обратите внимание, что в Windows PowerShell для параметров всегда предваряются дефис (-).</span><span class="sxs-lookup"><span data-stu-id="7b5a9-149">Note that, in Windows PowerShell, parameters are always prefaced with a dash (-).</span></span> <span data-ttu-id="7b5a9-150">Это означает, что для этого же командлета параметр Унассигнедусер будет указан с использованием следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="7b5a9-150">That means that, for this same cmdlet, the UnassignedUser parameter would be indicated by using this syntax:</span></span>
    
        -UnassignedUser
    
    <span data-ttu-id="7b5a9-151">Это полезно знать, но не только в том случае, если параметры должны быть обозначены дефисом, но Кроме того, так как это отличается от окна команд, где аргументы перед ними задаются с помощью косой черты (/).</span><span class="sxs-lookup"><span data-stu-id="7b5a9-151">This is useful to know, not only because parameters must be prefaced with a dash, but also because this differs from the command window, where arguments are prefaced using a forward slash (/):</span></span>
    
    ```console 
    /b
    ```

  - <span data-ttu-id="7b5a9-152">Значение параметра **kenmyer@litwareinc.com**.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-152">The parameter value **kenmyer@litwareinc.com**.</span></span>

<span data-ttu-id="7b5a9-153">Эта команда, кстати, возвращает сведения о конкретном пользователе: пользователь с удостоверением, kenmyer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="7b5a9-153">That command, incidentally, returns information about a specific user: the user with the identity, kenmyer@litwareinc.com.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="7b5a9-154">См. также</span><span class="sxs-lookup"><span data-stu-id="7b5a9-154">See Also</span></span>


<span data-ttu-id="7b5a9-155">[Введение в Windows PowerShell и Skype для бизнеса Online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7b5a9-155">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

