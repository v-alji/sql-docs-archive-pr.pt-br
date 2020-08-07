---
title: Executando Operação (Assistente de Importação e Exportação do SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.performingoperation.f1
ms.assetid: 83259509-71d6-4a64-a7f2-4e9603b30bd4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b6cdac605da2288149909a3fb6e9f245e10eebf8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575938"
---
# <a name="performing-operation-sql-server-import-and-export-wizard"></a><span data-ttu-id="0d436-102">Executando Operação (Assistente de Importação e Exportação do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0d436-102">Performing Operation (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="0d436-103">Use a página **executando operação** para exibir o progresso e os resultados da operação de importação/exportação e para interromper a operação, se necessário.</span><span class="sxs-lookup"><span data-stu-id="0d436-103">Use the **Performing Operation** page to view the progress and the results of the import/export operation, and to interrupt the operation if necessary.</span></span>  
  
 <span data-ttu-id="0d436-104">Para obter mais informações sobre este assistente, consulte [Assistente de Importação e Exportação do SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="0d436-104">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="0d436-105">Para saber mais sobre as opções de inicialização do assistente, bem como as permissões necessárias para executar o assistente com êxito, consulte [executar o assistente de importação e exportação do SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="0d436-105">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="0d436-106">O objetivo do Assistente de Importação e Exportação do SQL Server é copiar dados de uma origem para um destino.</span><span class="sxs-lookup"><span data-stu-id="0d436-106">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="0d436-107">O assistente também pode criar um banco de dados de destino e tabelas de destino para você.</span><span class="sxs-lookup"><span data-stu-id="0d436-107">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="0d436-108">No entanto, se for necessário copiar vários bancos de dados ou tabelas, ou outros tipos de objetos de banco de dados, será necessário usar o Assistente para Copiar Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="0d436-108">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="0d436-109">Para obter mais informações, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="0d436-109">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="0d436-110">Opções</span><span class="sxs-lookup"><span data-stu-id="0d436-110">Options</span></span>  
 <span data-ttu-id="0d436-111">**Ação**</span><span class="sxs-lookup"><span data-stu-id="0d436-111">**Action**</span></span>  
 <span data-ttu-id="0d436-112">Exibe cada ação que faz parte da operação.</span><span class="sxs-lookup"><span data-stu-id="0d436-112">Displays each action that is part of the operation.</span></span>  
  
 <span data-ttu-id="0d436-113">**Status**</span><span class="sxs-lookup"><span data-stu-id="0d436-113">**Status**</span></span>  
 <span data-ttu-id="0d436-114">Exibe o sucesso ou falha de cada ação.</span><span class="sxs-lookup"><span data-stu-id="0d436-114">Displays the success or failure of each action.</span></span>  
  
 <span data-ttu-id="0d436-115">**Message**</span><span class="sxs-lookup"><span data-stu-id="0d436-115">**Message**</span></span>  
 <span data-ttu-id="0d436-116">Exibe mensagens informativas e mensagens de erro que a ação pode gerar.</span><span class="sxs-lookup"><span data-stu-id="0d436-116">Displays informational and error messages that the action might generate.</span></span>  
  
 <span data-ttu-id="0d436-117">**Filter**</span><span class="sxs-lookup"><span data-stu-id="0d436-117">**Filter**</span></span>  
 <span data-ttu-id="0d436-118">Escolha se você quer exibir somente erros, avisos ou ações bem sucedidas.</span><span class="sxs-lookup"><span data-stu-id="0d436-118">Choose whether you want to display only errors, warnings, or successful actions.</span></span> <span data-ttu-id="0d436-119">Você pode reverter para a exibição padrão escolhendo **Mostrar todas as ações**.</span><span class="sxs-lookup"><span data-stu-id="0d436-119">You can revert to the default display by choosing **Show All Actions**.</span></span>  
  
 <span data-ttu-id="0d436-120">**Parar**</span><span class="sxs-lookup"><span data-stu-id="0d436-120">**Stop**</span></span>  
 <span data-ttu-id="0d436-121">Interrompa a operação, se necessário, usando o botão **parar** .</span><span class="sxs-lookup"><span data-stu-id="0d436-121">Interrupt the operation, if necessary, by using the **Stop** button.</span></span>  
  
 <span data-ttu-id="0d436-122">**Report**</span><span class="sxs-lookup"><span data-stu-id="0d436-122">**Report**</span></span>  
 <span data-ttu-id="0d436-123">Exibe o relatório, salve o relatório em um arquivo, copie-o para a área de transferência ou envie-o por email.</span><span class="sxs-lookup"><span data-stu-id="0d436-123">View a report of the results, save the report to a file, copy the report to the clipboard, or send the report by e-mail.</span></span>  
  
  
