---
title: Службы SQL Server Reporting Services (вызов)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a4ba8d6-ba43-45b3-b834-372d092561e7
description: После представления необходимых сведений для развертывания отчетов monitoring Server в Microsoft SQL Server R2 или службы отчетов Microsoft SQL Server 2012 г. на странице Execute Commands отображается сводка команд, выдающихся для установки отчетов в службы SQL Server отчетов.
ms.openlocfilehash: b861db053a8851b05ce72a08de6dfae39b9d3bfc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096855"
---
# <a name="sql-server-reporting-services-invoke"></a><span data-ttu-id="5db36-103">Службы SQL Server Reporting Services (вызов)</span><span class="sxs-lookup"><span data-stu-id="5db36-103">SQL Server Reporting Services (Invoke)</span></span>
 
<span data-ttu-id="5db36-104">После представления необходимых сведений для развертывания отчетов monitoring Server в Microsoft SQL Server R2 или службы отчетов Microsoft SQL Server 2012 г. на странице Execute Commands отображается сводка команд, выдающихся для установки отчетов в службы SQL Server отчетов.</span><span class="sxs-lookup"><span data-stu-id="5db36-104">After supplying the required information for the deployment of the Monitoring Server reports to the Microsoft SQL Server 2008 R2, or to Microsoft SQL Server 2012 Report Services, the page Execute Commands displays a summary of commands that are issued to install the reports to the SQL Server Reporting Services.</span></span>
  
<span data-ttu-id="5db36-p101">Просмотрите сводку команд и обратите внимание на все ошибки и предупреждения, показанные командами. Если создается журнал, выберите файл журнала из раскрывающегося списка в окне сводки и нажмите кнопку **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="5db36-p101">Review the summary of commands and note any error or warning messages displayed from the commands. If a log file is generated, select the log file from the drop-down list under the summary window, and click **View Log** to display the log file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5db36-107">Для успешного развертывания отчетов служб отчетности и получения доступа к отчетам после завершения развертывания необходимо открыть TCP/IP-порт 80 (и необязательно порт TCP 443 для SSL, если вы назначите сертификат службам отчетности) в брандмауэре Windows с расширенным обеспечением безопасности на SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5db36-107">For the Reporting Services reports to deploy successfully, and to access the reports after deployment is complete, you must have TCP/IP port 80 (and optionally, TCP port 443 for SSL, if you assign a certificate to the Reporting Services) open in the Windows Firewall with Advanced Security on the SQL Server.</span></span> <span data-ttu-id="5db36-108">Подробные сведения см. в материале [Настройка брандмауэра Windows для](/sql/sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access) SQL Server доступа Microsoft SQL Server R2 2008.</span><span class="sxs-lookup"><span data-stu-id="5db36-108">For details, see [Configure the Windows Firewall to Allow SQL Server Access](/sql/sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access) for Microsoft SQL Server 2008 R2.</span></span>
  
<span data-ttu-id="5db36-109">После просмотра сводки нажмите кнопку **Готово,** чтобы завершить установку отчетов в службы SQL Server отчетов.</span><span class="sxs-lookup"><span data-stu-id="5db36-109">After reviewing the summary, click **Finish** to complete the installation of the reports to the SQL Server Reporting Services.</span></span>
