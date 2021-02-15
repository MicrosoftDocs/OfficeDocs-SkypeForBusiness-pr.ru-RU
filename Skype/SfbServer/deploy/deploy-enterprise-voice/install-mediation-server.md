---
title: Установка файлов для сервера-посредника в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: Сводка. Узнайте, как установить файлы для сервера-посредника в Skype для бизнеса Server.
ms.openlocfilehash: 80f25d9fab37555d5b4e9dc3d610c5c9037c934d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830799"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="af1ca-103">Установка файлов для сервера-посредника в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="af1ca-103">Install the files for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="af1ca-104">**Сводка:** Узнайте, как установить файлы для сервера-посредника в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="af1ca-104">**Summary:** Learn how to install the files for Mediation Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="af1ca-105">Для успешного выполнения этой процедуры необходимо войти на сервер как минимум с учетной записью локального администратора и пользователя домена, которая является членом группы RTCUniversalReadOnlyAdmins или группы, имеющей более высокие привилегии.</span><span class="sxs-lookup"><span data-stu-id="af1ca-105">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>
  
<span data-ttu-id="af1ca-106">Воспользуйтесь действиями, которые необходимо выполнить в этом разделе, чтобы запустить мастер развертывания Skype для бизнеса Server, чтобы установить файлы сервера-посредника на компьютере, добавленном в пул серверов-посредников после использования построитель топологий для определения и публикации пула.</span><span class="sxs-lookup"><span data-stu-id="af1ca-106">Use the steps in this topic to run Skype for Business Server Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool after you have used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="af1ca-107">При установке файлов сервера-посредника также устанавливается и назначается сертификат, необходимый каждому компьютеру в пуле серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="af1ca-107">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="af1ca-108">В этом разделе предполагается, что вы уже определили и опубликовали автономный пул серверов-посредников в топологии, как описано в разделе "Развертывание сервера-посредника в построите топологию" в [Skype для бизнеса Server.](deploy-a-mediation-server.md)</span><span class="sxs-lookup"><span data-stu-id="af1ca-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool in your topology, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md).</span></span> 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="af1ca-109">Установка файлов для автономного пула серверов-посредников</span><span class="sxs-lookup"><span data-stu-id="af1ca-109">To install the files for a stand-alone Mediation Server pool</span></span>

1. <span data-ttu-id="af1ca-110">На установоковом носите щелкните правой кнопкой мыши\Setup\amd64\Setup.exeи выберите "Запуск _\<installation media\>_ \*\*\*\* **от администратора".**</span><span class="sxs-lookup"><span data-stu-id="af1ca-110">From the installation media, right-click  _\<installation media\>_ **\Setup\amd64\Setup.exe**, and then click **Run as Administrator**.</span></span>
    
2. <span data-ttu-id="af1ca-111">На странице **Папка установки** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="af1ca-111">On the **Installation Location** page, click **OK**.</span></span>
    
3. <span data-ttu-id="af1ca-p102">На странице **Лицензионное соглашение** нажмите кнопку **Принимаю**, а затем нажмите **ОК**. (Требуется для продолжения.)</span><span class="sxs-lookup"><span data-stu-id="af1ca-p102">On the **End User License Agreement** page, click **I accept**, and then click **OK**. (Required to continue.)</span></span>
    
4. <span data-ttu-id="af1ca-114">На странице мастера **развертывания Skype для бизнеса Server** щелкните "Установить или обновить систему Skype для бизнеса **Server".**</span><span class="sxs-lookup"><span data-stu-id="af1ca-114">On the **Skype for Business Server Deployment Wizard** page, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="af1ca-115">Рядом со строкой **Шаг 1. Установка локального хранилища конфигурации** нажмите кнопку **Выполнить** и следуйте инструкциям на экране.</span><span class="sxs-lookup"><span data-stu-id="af1ca-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>
    
6. <span data-ttu-id="af1ca-116">На странице **Настройка локальной реплики центрального хранилища управления** примите значение параметра **Извлечь данные непосредственно из центрального хранилища управления** по умолчанию и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="af1ca-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="af1ca-117">На странице **Выполнение команд**, когда состояние задачи отображается как **Завершено**, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="af1ca-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
8. <span data-ttu-id="af1ca-118">Рядом с **шагом 2: установка** или удаление компонентов Skype для бизнеса Server, нажмите кнопку **"Выполнить"** и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="af1ca-118">Next to **Step 2: Setup or Remove Skype for Business Server Components**, click **Run**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="af1ca-119">На странице **Выполнение команд**, когда состояние задачи отображается как **Завершено**, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="af1ca-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
10. <span data-ttu-id="af1ca-p103">Нажмите кнопку **Выполнить** рядом со строкой **Шаг 3. Запрос, установка и назначение сертификатов**. Следуйте инструкциям на экране, приняв значения по умолчанию. Для сервера-посредника требуется один сертификат, поэтому вы выполните **Шаг 3** дважды: один раз, чтобы издать нужный сертификат, и второй раз, чтобы его назначить.</span><span class="sxs-lookup"><span data-stu-id="af1ca-p103">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**. Follow the instructions on the screen, accepting the default settings. The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>
    
11. <span data-ttu-id="af1ca-123">После выдачи и корректного назначения сертификата нажмите рядом со строкой **Шаг 4. Запуск служб** кнопку **Выполнить** и следуйте инструкциям на экране.</span><span class="sxs-lookup"><span data-stu-id="af1ca-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>
    
12. <span data-ttu-id="af1ca-124">После успешного завершения **шага 4** перезапустите сервер и войдите на него как участник группы DomainAdmins.</span><span class="sxs-lookup"><span data-stu-id="af1ca-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>
    
13. <span data-ttu-id="af1ca-125">На компьютере, где запущена панель управления Skype  для бизнеса Server, убедитесь, что на странице "Топология" панели управления Skype для бизнеса Server отображается состояние службы сервера-посредника как зеленая метка.</span><span class="sxs-lookup"><span data-stu-id="af1ca-125">On the computer where you are running Skype for Business Server Control Panel, verify on the **Topology** page of Skype for Business Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="af1ca-126">Если вместо нее показан красный символ X, выберите сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="af1ca-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="af1ca-127">В меню **Действие** щелкните **Запустить все службы**.</span><span class="sxs-lookup"><span data-stu-id="af1ca-127">On the **Action** menu, click **Start All Services**.</span></span> 
    
<span data-ttu-id="af1ca-128">Если в пул серверов-посредников добавлено несколько компьютеров, выполните действия, выполняемые в этой процедуре, на всех остальных компьютерах в пуле серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="af1ca-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="af1ca-129">Если вам не нужно устанавливать файлы для сервера-посредника для каких-либо других компьютеров, выполните процедуры в настройках магистрали в Skype для бизнеса [Server,](configure-trunks.md) чтобы настроить параметры магистрали между этим пулом серверов-посредников (или всеми серверами-посредниками на сайте) и его одноранговой узел.</span><span class="sxs-lookup"><span data-stu-id="af1ca-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configure trunks in Skype for Business Server](configure-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

