---
title: Credenciais Oracle para executar scripts | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4a301cb0-2f5b-41ba-81bf-46b41d07f137
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 683b313e5b1065c3709c4637ddf968641612cc0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678907"
---
# <a name="oracle-credentials-for-running-script"></a><span data-ttu-id="27013-102">Credenciais Oracle para executar script</span><span class="sxs-lookup"><span data-stu-id="27013-102">Oracle Credentials for Running Script</span></span>
  <span data-ttu-id="27013-103">Para executar o script de log suplementar do console do Oracle CDC Designer, o programa solicita as credenciais do usuário Oracle que está executando o script.</span><span class="sxs-lookup"><span data-stu-id="27013-103">To run the Oracle supplemental logging script from the Oracle CDC Designer console, the program prompts you for the credentials of the Oracle user who is running the script.</span></span> <span data-ttu-id="27013-104">Para executar este script, o usuário Oracle deve ter permissão ALTER TABLE para todas as tabelas a serem capturadas e permissão SELECT na exibição DBA_LOG_GROUPS.</span><span class="sxs-lookup"><span data-stu-id="27013-104">To run this script, the Oracle user must have ALTER TABLE permission for all the tables to be captured and SELECT permission on the DBA_LOG_GROUPS view.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="27013-105">Lista de Tarefas</span><span class="sxs-lookup"><span data-stu-id="27013-105">Task List</span></span>  
 <span data-ttu-id="27013-106">Insira o seguinte nesta caixa de diálogo:</span><span class="sxs-lookup"><span data-stu-id="27013-106">Enter the following in this dialog box:</span></span>  
  
 <span data-ttu-id="27013-107">**Autenticação**</span><span class="sxs-lookup"><span data-stu-id="27013-107">**Authentication**</span></span>  
  
 <span data-ttu-id="27013-108">Selecione uma das seguintes:</span><span class="sxs-lookup"><span data-stu-id="27013-108">Select one of the following:</span></span>  
  
-   <span data-ttu-id="27013-109">**Autenticação do Windows**: selecione isto para usar as credenciais de domínio atuais do Windows.</span><span class="sxs-lookup"><span data-stu-id="27013-109">**Windows Authentication**: Select this to use the current Windows domain credentials.</span></span> <span data-ttu-id="27013-110">Você só poderá usar esta opção se o banco de dados Oracle estiver configurado para funcionar com autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="27013-110">You can use this option only if the Oracle database is configured to work with Windows authentication.</span></span>  
  
-   <span data-ttu-id="27013-111">**Autenticação do Oracle**: se você selecionou esta opção, deve digitar o **Nome de usuário** e **Senha** para o usuário no banco de dados Oracle de origem ao qual você está se conectando.</span><span class="sxs-lookup"><span data-stu-id="27013-111">**Oracle Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the Source Oracle database you are connecting to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27013-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="27013-112">See Also</span></span>  
 <span data-ttu-id="27013-113">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span><span class="sxs-lookup"><span data-stu-id="27013-113">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span></span>  
 [<span data-ttu-id="27013-114">Examinar e gerar scripts de log suplementares</span><span class="sxs-lookup"><span data-stu-id="27013-114">Review and Generate Supplemental Logging Scripts</span></span>](review-and-generate-supplemental-logging-scripts.md)  
  
  
