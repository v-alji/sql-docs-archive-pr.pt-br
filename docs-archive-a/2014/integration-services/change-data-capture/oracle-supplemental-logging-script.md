---
title: Script de log suplementar Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5e6ee618-b89b-46c7-92ad-4fc5ef7b777a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0aa55e71c17574eba9e25e098a3881b0eb4c9e11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678906"
---
# <a name="oracle-supplemental-logging-script"></a><span data-ttu-id="29d42-102">Script de log suplementar Oracle</span><span class="sxs-lookup"><span data-stu-id="29d42-102">Oracle Supplemental Logging Script</span></span>
  <span data-ttu-id="29d42-103">Essa caixa de diálogo mostra o script suplementar de registro em log do Oracle.</span><span class="sxs-lookup"><span data-stu-id="29d42-103">This dialog box shows the script the Oracle supplemental logging script.</span></span>  
  
 <span data-ttu-id="29d42-104">Quando você prepara uma Instância CDC para uso, o Designer de CDC cria um script Oracle SQL que configura o registro em log suplementar para as tabelas a serem capturadas.</span><span class="sxs-lookup"><span data-stu-id="29d42-104">When you prepare a CDC Instance for use, the CDC Designer creates an Oracle SQL script that sets up supplemental logging for the tables to be captured.</span></span> <span data-ttu-id="29d42-105">O script suplementar de registro em log diz ao Oracle que, quando uma tabela específica é atualizada, os registros de alteração que ele grava no log de transação deve conter os dados de todas as colunas de interesse, não apenas as colunas que foram alteradas.</span><span class="sxs-lookup"><span data-stu-id="29d42-105">The supplemental logging script tells Oracle that when a specific table is updated, the change records it writes to the transaction log should contain the data of all columns of interest, not just the columns that changed.</span></span>  
  
 <span data-ttu-id="29d42-106">Dependendo das políticas do DBA Oracle em sua organização, executar o script suplementar de registro em log pode exigir revisão e aprovação de um DBA da Oracle.</span><span class="sxs-lookup"><span data-stu-id="29d42-106">Depending on the Oracle DBA policies in your organization, running the supplemental logging script may require a review and approval by an Oracle DBA.</span></span>  
  
## <a name="options"></a><span data-ttu-id="29d42-107">Opções</span><span class="sxs-lookup"><span data-stu-id="29d42-107">Options</span></span>  
 <span data-ttu-id="29d42-108">Veja a seguir as opções disponíveis sobre como executar o script.</span><span class="sxs-lookup"><span data-stu-id="29d42-108">The following are the available options for how to execute the script.</span></span>  
  
 <span data-ttu-id="29d42-109">**Executar Script**</span><span class="sxs-lookup"><span data-stu-id="29d42-109">**Run Script**</span></span>  
 <span data-ttu-id="29d42-110">Executa o script suplementar de registro em log nas tabelas definidas para a instância CDC.</span><span class="sxs-lookup"><span data-stu-id="29d42-110">Runs the supplemental logging script on the tables defined for the CDC instance.</span></span> <span data-ttu-id="29d42-111">Para executar este script, o usuário Oracle deve ter permissão ALTER TABLE para todas as tabelas a serem capturadas e permissão SELECT na exibição DBA_LOG_GROUPS.</span><span class="sxs-lookup"><span data-stu-id="29d42-111">To run this script, the Oracle user must have ALTER TABLE permission for all the tables to be captured and SELECT permission on the DBA_LOG_GROUPS view.</span></span> <span data-ttu-id="29d42-112">Além disso, o usuário Oracle deve ter as credenciais para um uso de banco de dados Oracle com as permissões obrigatórias.</span><span class="sxs-lookup"><span data-stu-id="29d42-112">In addition, the Oracle user must have the credentials for an Oracle database use with the required permissions.</span></span> <span data-ttu-id="29d42-113">Você pode deixar o programa solicitar que você insira as credenciais do Oracle e, em seguida, executar o script.</span><span class="sxs-lookup"><span data-stu-id="29d42-113">You can let the program prompt you for the Oracle credentials and then have it run the script.</span></span>  
  
 <span data-ttu-id="29d42-114">**Salvar como**</span><span class="sxs-lookup"><span data-stu-id="29d42-114">**Save As**</span></span>  
 <span data-ttu-id="29d42-115">Salva o script em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="29d42-115">Saves the script to a text file.</span></span> <span data-ttu-id="29d42-116">Isto é usado se um administrador de banco de dados Oracle (DBA) precisar examinar e executar o script suplementar de registro em log. O programa deixa salvar o script em um arquivo de texto que você pode enviar posteriormente para o DBA da Oracle por email ou por outros meios para ser executa posteriormente (usando o utilitário SQL\*Plus Oracle ou outra ferramenta para executar scripts em um banco de dados Oracle).</span><span class="sxs-lookup"><span data-stu-id="29d42-116">This is used if an Oracle database administrator (DBA) needs to examine and execute the supplemental logging script, the program lets you save the script to a text file that you can later send to the Oracle DBA by email or by other means to be execute later (by using the SQL\*Plus Oracle utility or other tool for running scripts on an Oracle database).</span></span>  
  
 <span data-ttu-id="29d42-117">**Copy**</span><span class="sxs-lookup"><span data-stu-id="29d42-117">**Copy**</span></span>  
 <span data-ttu-id="29d42-118">Copiar o script para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="29d42-118">Copies the script to the clipboard.</span></span> <span data-ttu-id="29d42-119">Quando você estiver pronto, poderá colar o script em qualquer local necessário no caso de um administrador de banco de dados Oracle (DBA) precisa examinar e executar o script suplementar de registro em log.</span><span class="sxs-lookup"><span data-stu-id="29d42-119">When ready you can paste the script in any location you need in case an Oracle database administrator (DBA) needs to examine and execute the supplemental logging script.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29d42-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="29d42-120">See Also</span></span>  
 <span data-ttu-id="29d42-121">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span><span class="sxs-lookup"><span data-stu-id="29d42-121">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span></span>  
 [<span data-ttu-id="29d42-122">Gerenciar uma instância CDC</span><span class="sxs-lookup"><span data-stu-id="29d42-122">Manage a CDC Instance</span></span>](manage-a-cdc-instance.md)  
  
  
