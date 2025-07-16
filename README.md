
# フォルダ構成

```txt
my-databricks-bundle/
├── databricks.yml               # バンドルの定義（ルート）
├── .sqlfluff                    # ← SQLFluffの設定ファイル（ルート直下に置く）
├── .github/                     # GitHub Actions の設定フォルダ※なんかここあるとコミットプッシュできなくなる？？
│   └── workflows/
│       └── sql-lint.yml         # ← SQL構文チェック用のGitHub Actions定義
├── resources/                   # Databricks リソースの構成（YAML）
│   ├── jobs/
│   │   ├── bronze_to_silver_job.yml
│   │   └── silver_to_gold_job.yml
│   ├── clusters/
│   │   ├── dev_cluster.yml
│   │   └── prod_cluster.yml
│   ├── sql_warehouse/
│   │   └── prod_wh.yml         
│   └── pipelines/
│       └── my_pipeline.yml     # DLTやLakeflowのパイプライン定義
├── src/                         # ビジネスロジック（ノートブック、Python、SQL）
│   ├── bronze/
│   │   ├── load_raw_data.sql
│   │   └── clean_raw_data.py
│   ├── silver/
│   │   ├── transform_sales.sql
│   │   └── enrich_sales.py
│   ├── gold/
│   │   └── aggregate_metrics.sql
│   └── utils/
│       └── common_functions.py
├── tests/                       # ユニットテストや統合テスト
│   └── test_enrich_sales.py
└── README.md
```

# 非推奨事項（特別な事情がない限り行わないこと）
## 個人のアクセストークンは発行しない

## pip
バージョン指定を行わない
バージョン指定を粉わない場合自動的に安定板がインストールされます
