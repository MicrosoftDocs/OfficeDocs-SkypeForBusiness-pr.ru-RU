---
title: Установка средств администрирования в Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Summary: Learn how to install the administrative tools required for an installation of Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: c0d6b4a2ad41fbca4c89e6095a34eabf08e191ee
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="install-administrative-tools-in-skype-for-business-server-2015"></a>Установка средств администрирования в Skype для бизнеса Server 2015
 
**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
К средствам администрирования относятся построитель топологий и панель управления. The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server. Шаги с 1 по 5 могут выполняться в произвольном порядке. Но шаги 6, 7 и 8 должны выполняться в указанном порядке после шагов с 1 по 5, как показано на схеме. Установка средств администрирования — шаг 3 из 8.
  
![Обзорная схема](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-2015-administrative-tools"></a>Install Skype for Business Server 2015 administrative tools

The installation media for Skype for Business Server 2015 provides a flexible experience. When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell. By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment. Мастер развертывания автоматически запускается после установки основных компонентов. The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.
  
> [!IMPORTANT]
> Every Skype for Business Server environment must have at least one server with the administrative tools installed. 
  
Смотреть видеоруководство **Установка средств администрирования**.
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-2015-administrative-tools-from-the-deployment-wizard"></a>Install Skype for Business Server 2015 administrative tools from the Deployment Wizard

1. Insert the Skype for Business Server 2015 installation media. Если установка не началась автоматически, дважды щелкните файл **Setup**.
    
2. Для запуска установочного носителя требуется Microsoft Visual C++. Открывается диалоговое окно с запросом подтверждения установки. Нажмите **Да**.
    
3. By using Smart Setup, a new feature in Skype for Business Server 2015, you can connect to the Internet to check for updates during the installation process. Это повышает эффективность работы, так как вы можете быть уверены в получении самых последних обновлений продукта. Нажмите кнопку **Установить**, чтобы начать установку.
    
4. Внимательно просмотрите лицензионное соглашение. Если вы согласны, выберите **Я принимаю условия лицензионного соглашения** и нажмите кнопку **ОК**.
    
5. The Skype for Business Server 2015 Core Components will be installed on the server. 
    
    Состав основных компонентов показан на рисунке.
    
    ![Основные компоненты на экране приложений.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
  - **Skype for Business Server 2015 Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server 2015.
    
  - **Skype for Business Server 2015 Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server 2015.
    
    Once the installation of the Core Components is complete, the Skype for Business Server 2015 Deployment Wizard will automatically launch, as shown in the figure. 
    
    ![Мастер развертывания Skype для бизнеса Server 2015](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. In addition to the Core Components, you will also need to install Skype for Business Server 2015 Topology Builder and Skype for Business Server 2015 Control Panel on at least one server in the environment. Щелкните **Установить средства администрирования** в окне мастера развертывания.
    
7. Нажмите кнопку **Далее**, чтобы начать установку.
    
8. После завершения установки нажмите кнопку **Готово**. Теперь средства администрирования добавлены на сервер, как показано на рисунке.
    
    ![Средства администрирования Skype для бизнеса Server 2015](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype for Business Server 2015 Topology Builder** A program used to build, deploy, and manage topologies.
    
   - **Skype for Business Server 2015 Control Panel** A program used to administer the installation.
    

