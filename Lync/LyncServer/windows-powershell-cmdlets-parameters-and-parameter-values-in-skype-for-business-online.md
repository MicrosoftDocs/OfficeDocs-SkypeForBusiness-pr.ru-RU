---
title: Командлеты, параметры и значения параметров Windows PowerShell в Skype для бизнеса Online
description: Командлеты, параметры и значения параметров Windows PowerShell в Skype для бизнеса Online.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1500713a02f85384be5a9cd9a7338b58d3c365f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555455"
---
# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a><span data-ttu-id="ebff3-103">Командлеты, параметры и значения параметров Windows PowerShell в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="ebff3-103">Windows PowerShell cmdlets, parameters, and parameter values in Skype for Business Online</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebff3-104">_**Последнее изменение темы:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="ebff3-104">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="ebff3-105">Если вы знакомы с окном команд, которое находится во всех версиях Windows (или если вы знакомы с MS-DOS), то у вас будет головной старт, когда речь заходит о том, как использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ebff3-105">If you are familiar with the command window found in all versions of Windows (or if you are familiar with MS-DOS), then you’ll have a head start when it comes to learning how to use Windows PowerShell.</span></span> <span data-ttu-id="ebff3-106">В командной строке введите команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="ebff3-106">In the command window, you type a command and press ENTER.</span></span> <span data-ttu-id="ebff3-107">В ответ компьютер запускает команду или исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="ebff3-107">In response, the computer runs a command or an executable file.</span></span> <span data-ttu-id="ebff3-108">Например, чтобы получить сведения обо всех файлах и папках в текущем каталоге, введите эту команду в командной строки и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="ebff3-108">For example, to return information about all the files and folders in the current directory, you’d type this command at the command prompt and then press ENTER:</span></span>

```console
dir
```

<span data-ttu-id="ebff3-109">В свою очередь вы получаете сведения обо всех файлах и папках в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="ebff3-109">In turn, you get back information about all the files and folders in the current directory:</span></span>

```console
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

<span data-ttu-id="ebff3-110">Это один из примеров результатов, когда вы вводите только имя команды или исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="ebff3-110">That’s one example of a result when you do type only the name of a command or an executable file.</span></span> <span data-ttu-id="ebff3-111">Однако многие из команд, выполняемых в окне командной строки, также принимают *аргументы*.</span><span class="sxs-lookup"><span data-stu-id="ebff3-111">However, many of the commands that are run from within the command window also accept *arguments*.</span></span> <span data-ttu-id="ebff3-112">Аргументы — это дополнительные фрагменты данных, которые передаются в команду, что позволяет изменить поведение команды.</span><span class="sxs-lookup"><span data-stu-id="ebff3-112">Arguments are additional pieces of information that are passed to the command, which modify the behavior of the command.</span></span> <span data-ttu-id="ebff3-113">Например, если вы хотите просмотреть имена файлов и папок в текущем каталоге, не существует никакой другой информации, например размера файла или папки, а также даты и времени создания папки или папки.</span><span class="sxs-lookup"><span data-stu-id="ebff3-113">For example, if you only wanted to see the names of the files and folder in the current directory—no other information, such as the size of the file or folder, or the date and time that the folder or folder was created.</span></span> <span data-ttu-id="ebff3-114">В этом случае необходимо добавить аргумент **/b** при выполнении команды dir:</span><span class="sxs-lookup"><span data-stu-id="ebff3-114">In this case, you’d append the **/b** argument when running the dir command:</span></span>

```console
dir /b
```

<span data-ttu-id="ebff3-115">Когда вы включаете аргумент **/b** , команда **dir** сообщает только о именах папок и файлов, найденных в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="ebff3-115">When you include the **/b** argument, the **dir** command reports back only the names of the folders and files found in the current directory:</span></span>

```console
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
```

<span data-ttu-id="ebff3-116">В предыдущей команде аргумент **/b** — это единственная информация, необходимая для того, чтобы ограничить возвращаемые данные именами файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="ebff3-116">In the preceding command, the **/b** argument is the only information required to limit the returned data to file and folder names.</span></span> <span data-ttu-id="ebff3-117">Это часто относится к командам командной строки: достаточное присутствие аргумента — это все, что необходимо для изменения поведения команды.</span><span class="sxs-lookup"><span data-stu-id="ebff3-117">This is often the case with command-line commands: the mere presence of an argument is all that’s needed to change the command’s behavior.</span></span> <span data-ttu-id="ebff3-118">(То есть аргумент **/b** включается для скрытия дополнительной информации, или вы исключает аргумент **/b** для отображения дополнительной информации.) Однако в других случаях необходимо указать *значение аргумента*.</span><span class="sxs-lookup"><span data-stu-id="ebff3-118">(That is, you include the **/b** argument to hide additional information, or you exclude the **/b** argument to show the extra information.) At other times, however, you must specify an *argument value*.</span></span> <span data-ttu-id="ebff3-119">Значение аргумента — это дополнительная информация, которая передается самому аргументу.</span><span class="sxs-lookup"><span data-stu-id="ebff3-119">An argument value is additional information passed to the argument itself.</span></span> <span data-ttu-id="ebff3-120">Например, аргумент **/o** позволяет указать, как команда dir будет сортировать возвращенные данные.</span><span class="sxs-lookup"><span data-stu-id="ebff3-120">For instance, the **/o** argument enables you to specify how you would like the dir command to sort the returned data.</span></span> <span data-ttu-id="ebff3-121">Кроме того, можно использовать значение аргумента **e** для сортировки по расширению файла или значение аргумента **s** для сортировки по размеру файлов.</span><span class="sxs-lookup"><span data-stu-id="ebff3-121">Among other options, you can use the argument value **e** to sort by file extension or the argument value **s** to sort by file size.</span></span> <span data-ttu-id="ebff3-122">Например, эта команда сортирует возвращенные данные по расширению файла.</span><span class="sxs-lookup"><span data-stu-id="ebff3-122">For example, this command sorts the returned data by file extension.</span></span> <span data-ttu-id="ebff3-123">Обратите внимание, что значение аргумента **e** включается сразу после аргумента **/o** :</span><span class="sxs-lookup"><span data-stu-id="ebff3-123">Note how the argument value **e** is included immediately after the **/o** argument:</span></span>

```console
dir /oe
```

<span data-ttu-id="ebff3-124">В нашем примере возвращенные данные будут выглядеть так, как показано в алфавитном порядке по добавочному номеру файла:</span><span class="sxs-lookup"><span data-stu-id="ebff3-124">Using our sample folder, the returned data will look like this, with the files sorted alphabetically by file extension:</span></span>

```console
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

<span data-ttu-id="ebff3-125">Или, чтобы помочь точно определить, о чем мы говорим:</span><span class="sxs-lookup"><span data-stu-id="ebff3-125">Or, to help you pinpoint exactly what we are talking about:</span></span>

```console
setup.doc  
RHDSetup.exe  
pldok.log
```

<span data-ttu-id="ebff3-126">Несмотря на то, что Windows PowerShell использует другую терминологию, основной подход к работе с Windows PowerShell аналогичен работе с окном команд: вы вводите команды, добавляя аргументы и значения аргументов, а затем нажимаете клавишу ВВОД для выполнения этих команд.</span><span class="sxs-lookup"><span data-stu-id="ebff3-126">Although Windows PowerShell uses different terminology, the basic approach to working with Windows PowerShell is the same as working with the command window: you type commands, you include arguments and argument values as needed, and then you press ENTER to execute those commands.</span></span> <span data-ttu-id="ebff3-127">Как отмечалось ранее, в Windows PowerShell используется терминология, отличная от используемой командной командной оболочкой.</span><span class="sxs-lookup"><span data-stu-id="ebff3-127">As noted, however, Windows PowerShell does use a different terminology than the command shell uses.</span></span> <span data-ttu-id="ebff3-128">В Windows PowerShell выполняемые команды называются *командлетами*.</span><span class="sxs-lookup"><span data-stu-id="ebff3-128">In Windows PowerShell, the commands you execute are known as *cmdlets*.</span></span> <span data-ttu-id="ebff3-129">В свою очередь аргументы, передаваемые командлету, называются *параметрами*, а значения, передаваемые в параметр, называются *значениями параметров*.</span><span class="sxs-lookup"><span data-stu-id="ebff3-129">In turn, the arguments passed to a cmdlet are known as *parameters*, and the values passed to a parameter are known as *parameter values*.</span></span>

<span data-ttu-id="ebff3-130">Предыдущие определения довольно упрощены.</span><span class="sxs-lookup"><span data-stu-id="ebff3-130">The preceding definitions are somewhat simplified.</span></span> <span data-ttu-id="ebff3-131">Командлеты — это, по сути, мини-приложения, которые можно запускать только в среде Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ebff3-131">Cmdlets are essentially mini-applications that can be run only from within the Windows PowerShell environment.</span></span> <span data-ttu-id="ebff3-132">Тем не менее, вы также можете выполнять другие команды и приложения в Windows PowerShell, в том числе большинство команд и приложений, которые можно запускать из командного окна.</span><span class="sxs-lookup"><span data-stu-id="ebff3-132">However, you can also run other commands and applications from within Windows PowerShell, including most of the commands and applications that can be run from a command window.</span></span> <span data-ttu-id="ebff3-133">Например, если вы хотите запустить блокнот из Windows PowerShell, достаточно ввести следующую команду и нажать клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="ebff3-133">For example, if you want to start Notepad from within Windows PowerShell, all you need to do is type the following and press ENTER:</span></span>

```console
notepad.exe
```

<span data-ttu-id="ebff3-134">Тем не менее, когда дело касается управления Skype для бизнеса Online, большинство администраторов полагается на командлеты Windows PowerShell для выполнения административных задач.</span><span class="sxs-lookup"><span data-stu-id="ebff3-134">When it comes to managing Skype for Business Online, however, most administrators will rely on Windows PowerShell cmdlets to carry out administrative tasks.</span></span> <span data-ttu-id="ebff3-135">В данный момент существует очень мало других типов команд или приложений, которые можно использовать для управления Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="ebff3-135">At time, there are very few other types of commands or applications that can be used to manage Skype for Business Online.</span></span> <span data-ttu-id="ebff3-136">Иногда командлеты Skype для бизнеса Online можно использовать без дополнительных аргументов (как указано в разделе аргументы, которые называются параметрами в Windows PowerShell).</span><span class="sxs-lookup"><span data-stu-id="ebff3-136">Sometimes the Skype for Business Online cmdlets can be used without any additional arguments (, as noted, arguments are known as parameters in Windows PowerShell).</span></span> <span data-ttu-id="ebff3-137">Например, следующая команда вызывает командлет [Get – CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) без дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="ebff3-137">For example, the following command calls the [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet without any additional parameters.</span></span> <span data-ttu-id="ebff3-138">Команда возвращает сведения обо всех пользователях Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="ebff3-138">By itself, the command returns information about all of your Skype for Business Online users:</span></span>

```powershell
Get-CsOnlineUser
```

<span data-ttu-id="ebff3-139">Однако большинство командлетов Skype для бизнеса Online также принимают параметры (и значения параметров).</span><span class="sxs-lookup"><span data-stu-id="ebff3-139">However, most of the Skype for Business Online cmdlets also accept parameters (and parameter values).</span></span> <span data-ttu-id="ebff3-140">Рассмотрим следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ebff3-140">Consider the following command:</span></span>

```powershell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

<span data-ttu-id="ebff3-141">Эта команда состоит из трех частей:</span><span class="sxs-lookup"><span data-stu-id="ebff3-141">This command consists of three parts:</span></span>

  - <span data-ttu-id="ebff3-142">Командлет **Get – CsOnlineUser**.</span><span class="sxs-lookup"><span data-stu-id="ebff3-142">The cmdlet **Get-CsOnlineUser**.</span></span>

  - <span data-ttu-id="ebff3-143">Параметр Identity.</span><span class="sxs-lookup"><span data-stu-id="ebff3-143">The Identity parameter.</span></span> <span data-ttu-id="ebff3-144">Обратите внимание, что в Windows PowerShell параметрам всегда предшествует дефис (-).</span><span class="sxs-lookup"><span data-stu-id="ebff3-144">Note that, in Windows PowerShell, parameters are always prefaced with a dash (-).</span></span> <span data-ttu-id="ebff3-145">Это означает, что для этого же командлета параметр Унассигнедусер будет указан с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="ebff3-145">That means that, for this same cmdlet, the UnassignedUser parameter would be indicated by using this syntax:</span></span>
    
    ```powershell
    -UnassignedUser
    ```
    
    <span data-ttu-id="ebff3-146">Это полезно, но не только в том случае, если в параметрах должны присутствовать дефисы, а также, так как это отличается от командного окна, где аргументы перед ними задаются с помощью косой черты (/):</span><span class="sxs-lookup"><span data-stu-id="ebff3-146">This is useful to know, not only because parameters must be prefaced with a dash, but also because this differs from the command window, where arguments are prefaced using a forward slash (/):</span></span>
    
    ```console
    /b
    ```

  - <span data-ttu-id="ebff3-147">Значение параметра **kenmyer@litwareinc.com**.</span><span class="sxs-lookup"><span data-stu-id="ebff3-147">The parameter value **kenmyer@litwareinc.com**.</span></span>

<span data-ttu-id="ebff3-148">Эта команда в случае необходимости возвращает сведения об определенном пользователе: пользователя с идентификатором kenmyer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="ebff3-148">That command, incidentally, returns information about a specific user: the user with the identity, kenmyer@litwareinc.com.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ebff3-149">См. также</span><span class="sxs-lookup"><span data-stu-id="ebff3-149">See Also</span></span>


<span data-ttu-id="ebff3-150">[Введение в Windows PowerShell и Skype для бизнеса Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ebff3-150">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

