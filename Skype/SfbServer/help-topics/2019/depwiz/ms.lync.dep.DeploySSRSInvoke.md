---
title: Службы SQL Server Reporting Services (вызов)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeploySSRSInvoke
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4a4ba8d6-ba43-45b3-b834-372d092561e7
ROBOTS: NOINDEX, NOFOLLOW
description: После получения необходимых сведений о развертывании отчетов сервера мониторинга в службы отчетов Microsoft SQL Server 2008 R2 или служб отчетов Microsoft SQL Server 2012 на странице "Выполнение команд" отображается сводка команд, которые выданы для установки отчетов в службы SQL Server Reporting Services.
ms.openlocfilehash: 560bda7437103db9ca322176c8cf98340a611f05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808789"
---
# <a name="sql-server-reporting-services-invoke"></a><span data-ttu-id="66fe2-103">Службы SQL Server Reporting Services (вызов)</span><span class="sxs-lookup"><span data-stu-id="66fe2-103">SQL Server Reporting Services (Invoke)</span></span>
 
<span data-ttu-id="66fe2-104">После представления необходимых сведений о развертывании отчетов сервера мониторинга в службы отчетов Microsoft SQL Server на странице "Выполнение команд" отображается сводка команд, которые выданы для установки отчетов в службы SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="66fe2-104">After supplying the required information for the deployment of the Monitoring Server reports to the Microsoft SQL Server Report Services, the page Execute Commands displays a summary of commands that are issued to install the reports to the SQL Server Reporting Services.</span></span>
  
<span data-ttu-id="66fe2-p101">Просмотрите сводку команд и обратите внимание на все ошибки и предупреждения, показанные командами. Если создается журнал, выберите файл журнала из раскрывающегося списка в окне сводки и нажмите кнопку **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="66fe2-p101">Review the summary of commands and note any error or warning messages displayed from the commands. If a log file is generated, select the log file from the drop-down list under the summary window, and click **View Log** to display the log file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="66fe2-107">Для успешного развертывания отчетов Службы Reporting Services и доступа к отчетам после завершения развертывания необходимо открыть TCP/IP-порт 80 (и, при желании, TCP-порт 443 для SSL, если вы назначите сертификат службам reporting Services) в брандмауэре Windows с дополнительной безопасностью на SQL Server.</span><span class="sxs-lookup"><span data-stu-id="66fe2-107">For the Reporting Services reports to deploy successfully, and to access the reports after deployment is complete, you must have TCP/IP port 80 (and optionally, TCP port 443 for SSL, if you assign a certificate to the Reporting Services) open in the Windows Firewall with Advanced Security on the SQL Server.</span></span> <span data-ttu-id="66fe2-108">Подробные сведения см. в подсети "Настройка брандмауэра [Windows для](https://go.microsoft.com/fwlink/p/?linkId=218031) SQL Server доступа Microsoft SQL Server 2008 R2".</span><span class="sxs-lookup"><span data-stu-id="66fe2-108">For details, see [Configure the Windows Firewall to Allow SQL Server Access](https://go.microsoft.com/fwlink/p/?linkId=218031) for Microsoft SQL Server 2008 R2.</span></span>
  
<span data-ttu-id="66fe2-109">После просмотра сводки нажмите кнопку **"Готово",** чтобы завершить установку отчетов в SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="66fe2-109">After reviewing the summary, click **Finish** to complete the installation of the reports to the SQL Server Reporting Services.</span></span>
  

