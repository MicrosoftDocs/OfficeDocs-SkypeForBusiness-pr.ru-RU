---
title: Расширитель общих настроек сервера архивации
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
ROBOTS: NOINDEX, NOFOLLOW
description: Для изменения свойств отдельного сервера мониторинга в построителе топологий можно щелкнуть правой кнопкой мыши сервер мониторинга в дереве консоли и выбрать Действие на панели инструментов или щелкнуть задачу на панели действий, затем щелкнуть Изменение свойств и изменить любые из следующих параметров.
ms.openlocfilehash: 6419b7b4fff2c533a0dc91ab0819b0a58044447d
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21060114"
---
# <a name="archiving-server-general-settings-expander"></a><span data-ttu-id="61643-103">Расширитель общих настроек сервера архивации</span><span class="sxs-lookup"><span data-stu-id="61643-103">Archiving Server General Settings Expander</span></span>
 
<span data-ttu-id="61643-104">Для изменения свойств отдельного сервера мониторинга в построителе топологий можно щелкнуть правой кнопкой мыши сервер мониторинга в дереве консоли и выбрать **Действие** на панели инструментов или щелкнуть задачу на панели действий, затем щелкнуть **Изменение свойств** и изменить любые из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="61643-104">In Topology Builder, you can edit the properties for an individual server running Archiving either by right-clicking the server running Archiving in the console tree and clicking **Action** in the toolbar, or by clicking a task in the Actions pane, and then clicking **Edit Properties** and changing any of the following options:</span></span>
  
- <span data-ttu-id="61643-105">**Полное доменное имя**. Служит для изменения полного доменного имени сервера, развертываемого для выполнения функции архивации.</span><span class="sxs-lookup"><span data-stu-id="61643-105">**FQDN**, to change the fully qualified domain name (FQDN) of the server that you want to deploy as an Server running Archiving.</span></span>
    
- <span data-ttu-id="61643-p101">**Хранилище SQL**. Служит для изменения экземпляра SQL Server, предназначенного для архивации базы данных SQL Server. Изменение базы данных SQL Server для сервера с функцией архивации вступает в силу только после перезагрузки этого сервера.</span><span class="sxs-lookup"><span data-stu-id="61643-p101">**SQL store**, to change the instance of SQL Server to be used for the archiving SQL Server database. If you change the SQL Server database of a server running Archiving, you must restart the server running Archiving to make sure that the change takes effect.</span></span>
    
- <span data-ttu-id="61643-p102">**Общий файловый ресурс**. Служит для изменения папки, предназначенной для архивации хранилища файлов. Изменение общего файлового ресурса для сервера с функцией архивации вступает в силу только после перезагрузки этого сервера. Кроме того, во избежание потери архивных файлов предыдущих конференций необходимо переместить их в папку нового хранилища файлов.</span><span class="sxs-lookup"><span data-stu-id="61643-p102">**File share**, to change the folder to be used for the archiving file store. If you change the file share of a Server running Archiving, you must restart the Server running Archiving to make sure that the change takes effect. Additionally, you must move previous conference files to the new file store folder to avoid loss of archived conference files.</span></span>
    
> [!NOTE]
> <span data-ttu-id="61643-111">Для изменения пулов, связанных с сервером, где выполняется функция архивации, выберите команду **Изменение свойств** для отдельного узла пула переднего плана или устройства обеспечения связи в филиалах, который на данный момент связан с сервером, где выполняется функция архивации.</span><span class="sxs-lookup"><span data-stu-id="61643-111">To change the pools associated with a server running Archiving, select the **Edit Properties** option for the individual Front End pool node or Survivable Branch Appliance node that is currently associated with the server running Archiving.</span></span>
  
> [!NOTE]
> <span data-ttu-id="61643-p103">Узел архивации содержит сервер с функцией архивации, если он ранее добавлен к топологии с помощью построителя топологий. В списке можно изменить свойства любого сервера с функцией архивации. Однако архивация мгновенных сообщений и сообщений веб-конференций возможна только после настройки соответствующей службы для сервера с функцией архивации.</span><span class="sxs-lookup"><span data-stu-id="61643-p103">The Archiving node contains a server running Archiving if you have previously added a server running Archiving to the topology in Topology Builder. You can edit properties for any server running Archiving in the list. However, instant messaging or web conferencing (messaging) cannot be archived until you also set up the service for the server running Archiving.</span></span> 
  

