---
title: Расширитель настроек службы сервера-посредника для Lync Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: Свойства службы посредника можно изменить, определив следующие свойства
ms.openlocfilehash: d8529a97459de70270fbe709d06c92e5a1b37af3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="26954-103">Расширитель настроек службы сервера-посредника для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="26954-103">Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="26954-104">Свойства службы посредника можно изменить, определив следующие свойства</span><span class="sxs-lookup"><span data-stu-id="26954-104">You edit the properties of the Mediation service by defining the following properties:</span></span>
  
- <span data-ttu-id="26954-p101">**Порты прослушивания**. Задайте порт **TLS** для ожидания передачи данных службой-посредником. По умолчанию для протокола TLS применяется порт TCP 5067.</span><span class="sxs-lookup"><span data-stu-id="26954-p101">**Listening ports**: Define the **TLS** port that the Mediation service will listen on. By default, the port value is TCP 5067 over transport layer security (TLS)</span></span>
    
    <span data-ttu-id="26954-p102">При необходимости можно задать значение порта **TCP**. Значение по умолчанию: TCP 5068.</span><span class="sxs-lookup"><span data-stu-id="26954-p102">Optionally, you define a **TCP** port value. By default, the value is TCP 5068.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="26954-p103">Для задания значения порта TCP необходимо выбрать режим **Включить порт TCP**. Требования к параметрам порта для связи со службой-посредником см. в документации по шлюзу ТСОП или IP‑УАТС.</span><span class="sxs-lookup"><span data-stu-id="26954-p103">The TCP port value setting is enabled by selecting **Enable TCP port**. You should refer to the documentation for your Public Switched Telephone Network (PSTN) Gateway or Internet Protocol Private Branch Exchange (IP-PBX) for the requirements for the port settings required to communicate with the Mediation service.</span></span> 
  
- <span data-ttu-id="26954-111">Выбор режима **Включить порт TCP** позволяет задать значение порта для передачи данных по протоколу TCP из шлюза ТСОП или IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="26954-111">You **Enable TCP port** to define the port value for TCP communications from your PSTN gateway or IP-PBX.</span></span>
    
- <span data-ttu-id="26954-112">Список связанных и существующих значений параметров **Линия связи** (т. е. магистрали для протокола SIP), **Шлюз** (шлюз ТСОП или IP-УАТС) и **Сайт** (сайт, настроенный для магистрали и шлюза).</span><span class="sxs-lookup"><span data-stu-id="26954-112">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="26954-p104">Выберите магистраль, шлюз и сайт, затем щелкните **По умолчанию** для применения выбранных значения по умолчанию данной службой-посредником. Для отмены применения значения по умолчанию выберите его и щелкните **Отменить по умолчанию**. После этого выберите новое значение для применения по умолчанию и щелкните **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="26954-p104">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
 <span data-ttu-id="26954-116">**ОК**. Принятие и фиксация изменений, внесенных в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="26954-116">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="26954-117">**Отмена**. Отмена изменений и закрытие диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="26954-117">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="26954-118">**Справка**. Отображение этого экрана справки.</span><span class="sxs-lookup"><span data-stu-id="26954-118">**Help** Displays this help screen.</span></span>
  

