---
title: Adicionar uma fonte de dados (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data sources [ODBC]
ms.assetid: b4ac6f0e-8e6a-4b1a-9a7e-60e0a69b2180
author: rothja
ms.author: jroth
ms.openlocfilehash: 519990e9dd9d84f75c4efc6c76b910f0a359f52f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572049"
---
# <a name="add-a-data-source-odbc"></a><span data-ttu-id="38e90-102">Adicionar uma fonte de dados (ODBC)</span><span class="sxs-lookup"><span data-stu-id="38e90-102">Add a Data Source (ODBC)</span></span>
  <span data-ttu-id="38e90-103">Você pode adicionar uma fonte de dados usando o Administrador ODBC, programaticamente (usando [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md)) ou criando um arquivo.</span><span class="sxs-lookup"><span data-stu-id="38e90-103">You can add a data source by using ODBC Administrator, programmatically (by using [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md)), or by creating a file.</span></span>  
  
### <a name="to-add-a-data-source-by-using-odbc-administrator"></a><span data-ttu-id="38e90-104">Para adicionar uma fonte de dados usando o Administrador ODBC</span><span class="sxs-lookup"><span data-stu-id="38e90-104">To add a data source by using ODBC Administrator</span></span>  
  
1.  <span data-ttu-id="38e90-105">No **painel de controle**, acesse **Ferramentas administrativas** e, em seguida, **fontes de dados (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="38e90-105">From the **Control Panel**, access **Administrative Tools** and then **Data Sources (ODBC)**.</span></span> <span data-ttu-id="38e90-106">Como alternativa, você pode invocar odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="38e90-106">Alternatively, you can invoke odbcad32.exe.</span></span>  
  
2.  <span data-ttu-id="38e90-107">Clique na **guia DSN do usuário**, DSN do **sistema**ou **DSN de arquivo** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="38e90-107">Click the **User DSN**, **System DSN**, or **File DSN** tab, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="38e90-108">Clique em **SQL Server**e em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="38e90-108">Click **SQL Server**, and then click **Finish**.</span></span>  
  
4.  <span data-ttu-id="38e90-109">Conclua as etapas no Assistente para Criação de Nova Fonte de Dados no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="38e90-109">Complete the Steps in the Create a New Data Source to SQL Server Wizard.</span></span>  
  
### <a name="to-add-a-data-source-programmatically"></a><span data-ttu-id="38e90-110">Para adicionar uma fonte de dados via programação</span><span class="sxs-lookup"><span data-stu-id="38e90-110">To add a data source programmatically</span></span>  
  
1.  <span data-ttu-id="38e90-111">Chame [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md) com o segundo parâmetro definido como ODBC_ADD_DSN ou ODBC_ADD_SYS_DSN.</span><span class="sxs-lookup"><span data-stu-id="38e90-111">Call [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md) with the second parameter set to either ODBC_ADD_DSN or ODBC_ADD_SYS_DSN.</span></span>  
  
### <a name="to-add-a-file-data-source"></a><span data-ttu-id="38e90-112">Para adicionar uma fonte de dados de arquivo</span><span class="sxs-lookup"><span data-stu-id="38e90-112">To add a file data source</span></span>  
  
1.  <span data-ttu-id="38e90-113">Chame [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) com um parâmetro SAVEFILE = file_name na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="38e90-113">Call [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) with a SAVEFILE=file_name parameter in the connect string.</span></span> <span data-ttu-id="38e90-114">Se a conexão for bem-sucedida, o driver ODBC criará uma fonte de dados de arquivo com os parâmetros de conexão no local apontado pelo parâmetro SAVEFILE.</span><span class="sxs-lookup"><span data-stu-id="38e90-114">If the connect is successful, the ODBC driver creates a file data source with the connection parameters in the location pointed to by the SAVEFILE parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38e90-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="38e90-115">See Also</span></span>  
 [<span data-ttu-id="38e90-116">Tópicos de instrução sobre a configuração do driver ODBC do SQL Server</span><span class="sxs-lookup"><span data-stu-id="38e90-116">Configuring the SQL Server ODBC Driver How-to Topics</span></span>](../../database-engine/dev-guide/configuring-the-sql-server-odbc-driver-how-to-topics.md)  
  
  
