---
title: Установка или удаление компонентов Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainBootstrap
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8813f25-eafa-4006-a186-94e4ebcc5ac7
description: Чтобы установить и активировать или отключить или удалить компоненты Skype для бизнеса Server 2015, используйте шаг 2. Установка или удаление компонентов Skype Server. Необходимо войти в систему с учетной записи локального администратора на устанавливаемом или изменяемом компьютере, а также иметь возможность чтения пользователей и групп доменных служб Active Directory в текущем домене. Чтобы начать, нажмите кнопку "Выполнить". При этом считыется определение топологии на основе центрального банка управления. Необходимые программные компоненты устанавливаются и настраиваются в соответствии с ролью, определенной в центральном хранилище управления. После завершения установки просмотрите сводку и нажмите кнопку "Готово".
ms.openlocfilehash: 05144357e7346428c6c23f6482abd91a58e3779f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829629"
---
# <a name="setup-or-remove-skype-for-business-server-components"></a><span data-ttu-id="297c2-108">Установка или удаление компонентов Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="297c2-108">Setup or Remove Skype for Business Server Components</span></span>
 
<span data-ttu-id="297c2-109">Чтобы установить и активировать или отключить или удалить компоненты Skype для бизнеса Server 2015, используйте шаг **2. Установка** или удаление компонентов Skype Server.</span><span class="sxs-lookup"><span data-stu-id="297c2-109">To install and activate, or deactivate or uninstall Skype for Business Server 2015 components, you use **Step 2: Setup or Remove Skype Server Components**.</span></span> <span data-ttu-id="297c2-110">Необходимо войти в систему с учетной записи локального администратора на устанавливаемом или изменяемом компьютере, а также иметь возможность чтения пользователей и групп доменных служб Active Directory в текущем домене.</span><span class="sxs-lookup"><span data-stu-id="297c2-110">You must be logged in as a local administrator on the computer that you are installing or modifying and must be able to read Active Directory Domain Services users and groups in the current domain.</span></span> <span data-ttu-id="297c2-111">Чтобы начать, нажмите кнопку **"Выполнить".**</span><span class="sxs-lookup"><span data-stu-id="297c2-111">To begin, click **Run**.</span></span> <span data-ttu-id="297c2-112">При этом считыется определение топологии на основе центрального банка управления.</span><span class="sxs-lookup"><span data-stu-id="297c2-112">When you do this, the Central Management store-based topology definition is read.</span></span> <span data-ttu-id="297c2-113">Необходимые программные компоненты устанавливаются и настраиваются в соответствии с ролью, определенной в центральном хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="297c2-113">Necessary software components are installed and configured, according to the role as defined in the Central Management store.</span></span> <span data-ttu-id="297c2-114">После завершения установки просмотрите сводку и нажмите кнопку **"Готово".**</span><span class="sxs-lookup"><span data-stu-id="297c2-114">When the installation is complete, review the Summary, and click **Finish**.</span></span>
  
> [!TIP]
> <span data-ttu-id="297c2-115">Если вам нужно просмотреть файлы журналов, созданные мастером развертывания, их можно найти на компьютере, где был запускался мастер развертывания, в каталоге Users пользователя Active Directory, который запустил этот шаг.</span><span class="sxs-lookup"><span data-stu-id="297c2-115">If you need to review the log files that are created by the Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="297c2-116">Например, если пользователь вошел с учетной записью администратора домена в домене Contoso.net, файлы журнала будут расположены в папке: > C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="297c2-116">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: > C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  
> [!NOTE]
> <span data-ttu-id="297c2-117">Если на этом компьютере ранее установлены компоненты Skype для бизнеса Server 2015, мастер развертывания распознает это, и кнопка на шаге 2 будет отображаться как "Снова **выполнить".**</span><span class="sxs-lookup"><span data-stu-id="297c2-117">If you have previously installed Skype for Business Server 2015 components on this computer, the Deployment Wizard will recognize this, and the button in step 2 will be displayed as **Run Again**.</span></span> <span data-ttu-id="297c2-118">Она позволяет выполнять шаг столько раз, сколько необходимо для правильной настройки или модификации сервера.</span><span class="sxs-lookup"><span data-stu-id="297c2-118">This enables you to run the step as many times as needed to correctly configure or modify the server.</span></span> 
  

