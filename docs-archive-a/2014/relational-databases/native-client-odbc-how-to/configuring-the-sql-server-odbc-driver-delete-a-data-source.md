---
title: Excluir uma fonte de dados (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data sources [ODBC]
ms.assetid: 910e3e16-7b91-49d8-80bb-b4243926afaa
author: rothja
ms.author: jroth
ms.openlocfilehash: 6e8acd6414b39b317ff0fcfe1b7b9fbab38ae0a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572047"
---
# <a name="delete-a-data-source-odbc"></a><span data-ttu-id="8ef71-102">Excluir uma fonte de dados (ODBC)</span><span class="sxs-lookup"><span data-stu-id="8ef71-102">Delete a Data Source (ODBC)</span></span>
  <span data-ttu-id="8ef71-103">Você pode excluir uma fonte de dados usando o Administrador ODBC, programaticamente (usando [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md)) ou excluindo um arquivo (se for um nome de fonte de dados de arquivo).</span><span class="sxs-lookup"><span data-stu-id="8ef71-103">You can delete a data source by using ODBC Administrator, programmatically (by using [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md)), or by deleting a file (if a file data source name).</span></span>  
  
### <a name="to-delete-a-data-source-by-using-odbc-administrator"></a><span data-ttu-id="8ef71-104">Para excluir uma fonte de dados usando o Administrador de ODBC</span><span class="sxs-lookup"><span data-stu-id="8ef71-104">To delete a data source by using ODBC Administrator</span></span>  
  
1.  <span data-ttu-id="8ef71-105">No **painel de controle**, abra **Ferramentas administrativas**e clique duas vezes em **fontes de dados (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="8ef71-105">In **Control Panel**, open **Administrative Tools**, and then double-click **Data Sources (ODBC)**.</span></span> <span data-ttu-id="8ef71-106">Alternativamente, você pode executar odbcad32.exe no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="8ef71-106">Alternatively, you can run odbcad32.exe from the command prompt.</span></span>  
  
2.  <span data-ttu-id="8ef71-107">Clique na guia **DSN do usuário**, DSN do **sistema**ou DSN de **arquivo** .</span><span class="sxs-lookup"><span data-stu-id="8ef71-107">Click the **User DSN**, **System DSN**, or **File DSN** tab.</span></span>  
  
3.  <span data-ttu-id="8ef71-108">Clique na fonte de dados para excluir.</span><span class="sxs-lookup"><span data-stu-id="8ef71-108">Click the data source to delete.</span></span>  
  
4.  <span data-ttu-id="8ef71-109">Clique em **remover**e confirme a exclusão.</span><span class="sxs-lookup"><span data-stu-id="8ef71-109">Click **Remove**, and then confirm the deletion.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ef71-110">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8ef71-110">Example</span></span>  
 <span data-ttu-id="8ef71-111">Para excluir programaticamente uma fonte de dados, chame [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md) usando ODBC_REMOVE_DSN ou ODBC_REMOVE_SYS_DSN como o segundo parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8ef71-111">To programmatically delete a data source, call [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md) using either ODBC_REMOVE_DSN or ODBC_REMOVE_SYS_DSN as the second parameter.</span></span>  
  
 <span data-ttu-id="8ef71-112">O exemplo a seguir mostra como você pode excluir programaticamente uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="8ef71-112">The following sample shows how you can programmatically delete a data source.</span></span>  
  
```  
// remove_odbc_data_source.cpp  
// compile with: ODBCCP32.lib user32.lib  
#include <iostream>  
#include <windows.h>  
#include <odbcinst.h>  
  
int main() {   
   LPCSTR provider = "SQL Server";   // Windows SQL Server Driver  
   LPCSTR provider = "SQL Server";   // Windows SQL Server driver  
   LPCSTR provider2 = "SQL Server Native Client 11.0";   // SQL Server 2012 Native Client driver  
   LPCSTR dsnname = "DSN=data2";  
   BOOL retval = SQLConfigDataSource(NULL, ODBC_REMOVE_DSN, provider, dsnname);  
   std::cout << retval;   // 1 if successful  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="8ef71-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8ef71-113">See Also</span></span>  
 [<span data-ttu-id="8ef71-114">Tópicos de instrução sobre a configuração do driver ODBC do SQL Server</span><span class="sxs-lookup"><span data-stu-id="8ef71-114">Configuring the SQL Server ODBC Driver How-to Topics</span></span>](../../database-engine/dev-guide/configuring-the-sql-server-odbc-driver-how-to-topics.md)  
  
  
