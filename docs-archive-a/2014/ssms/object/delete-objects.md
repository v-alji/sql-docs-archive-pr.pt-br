---
title: Excluir objetos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.deleteobjects.f1
helpviewer_keywords:
- Delete Objects dialog box
ms.assetid: 49541441-179c-40d3-ba0c-01bcae545984
author: stevestein
ms.author: sstein
ms.openlocfilehash: e7b20d1eee3e48c5531b6b788e125b943f7606d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568322"
---
# <a name="delete-objects"></a><span data-ttu-id="ea909-102">Excluir Objetos</span><span class="sxs-lookup"><span data-stu-id="ea909-102">Delete Objects</span></span>
  <span data-ttu-id="ea909-103">Use essa caixa de diálogo para excluir um banco de dados ou objeto de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ea909-103">Use this dialog box to delete a database or database object.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="ea909-104">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="ea909-104">UI element list</span></span>  
 <span data-ttu-id="ea909-105">**Objeto a ser excluído**</span><span class="sxs-lookup"><span data-stu-id="ea909-105">**Object to be deleted**</span></span>  
 <span data-ttu-id="ea909-106">Exibe os nomes, os tipos, os proprietários e o status dos objetos a serem excluídos, bem como qualquer mensagem sobre erros durante a execução.</span><span class="sxs-lookup"><span data-stu-id="ea909-106">Displays the names, types, owners, and status of the objects that are about to be deleted, as well as any messages about errors during execution.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ea909-107">Executar **Excluir** em um banco de dados é equivalente a emitir DROP DATABASE em [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea909-107">Running **Delete** on a database is equivalent to issuing DROP DATABASE in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ea909-108">**Mostrar Dependências**</span><span class="sxs-lookup"><span data-stu-id="ea909-108">**Show Dependencies**</span></span>  
 <span data-ttu-id="ea909-109">Clique para exibir os objetos que são dependentes do objeto selecionado atualmente e os objetos dos quais o objeto selecionado é dependente (dependência ascendente e descendente).</span><span class="sxs-lookup"><span data-stu-id="ea909-109">Click to display both the objects that are dependent on the currently selected object and objects that the current object is dependent on (upward and downward dependency).</span></span> <span data-ttu-id="ea909-110">As informações exibidas na caixa de diálogo **Mostrar Dependências** são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="ea909-110">The information displayed in the **Show Dependencies** dialog box is read-only.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ea909-111">O botão **Mostra Dependências** não aparece para todos os tipos de objetos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ea909-111">The **Show Dependencies** button does not appear for all types of database objects.</span></span> <span data-ttu-id="ea909-112">Para exibir as dependências quando o botão **Mostrar Dependências** não está disponível, clique com o botão direito do mouse no Pesquisador de Objetos e em **Exibir Dependências**.</span><span class="sxs-lookup"><span data-stu-id="ea909-112">To view dependencies when the **Show Dependencies** button is not available, right-click the object in Object Explorer, and then click **View Dependencies**.</span></span>  
  
 <span data-ttu-id="ea909-113">**Exclua informações de backup e de histórico de restauração para os bancos de dados**</span><span class="sxs-lookup"><span data-stu-id="ea909-113">**Delete backup and restore history information for databases**</span></span>  
 <span data-ttu-id="ea909-114">Aparece somente quando um banco de dados é excluído, essa caixa de seleção faz com que o backup e o histórico de restauração do banco de dados de assunto sejam excluídos do banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="ea909-114">Only appears when a database is deleted, this check box causes the backup and restore history for the subject database to be deleted from the **msdb** database.</span></span>  
  
 <span data-ttu-id="ea909-115">**Encerre as conexões existentes**</span><span class="sxs-lookup"><span data-stu-id="ea909-115">**Close existing connections**</span></span>  
 <span data-ttu-id="ea909-116">Aparece somente quando um banco de dados é excluído, essa caixa de seleção encerra as conexões com o banco de dados de assunto.</span><span class="sxs-lookup"><span data-stu-id="ea909-116">Only appears when a database is deleted, this check box terminates connections to the subject database.</span></span>  
  
  
