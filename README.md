trading_engine/
│
├── data_ingestion/             # Microservice 1: Raw market data (API/cache)
│   ├── __init__.py
│   ├── ingestion_service.py
│   ├── config.py
│   ├── sources/                # Data source adapters (APIs)
│   │   ├── __init__.py
│   │   ├── yahoo.py
│   │   ├── alpha_vantage.py
│   │   └── base.py            # Abstract DataSource interface
│   ├── storage/                # Saving/loading data
│   │   ├── __init__.py
│   │   ├── local.py
│   │   └── redis_cache.py
│   ├── utils/
│   │   ├── __init__.py
│   │   ├── normalizer.py
│   │   ├── validator.py
│   │   └── scheduler.py
│   └── main.py
│
├── feature_engineering/        # Microservice 2: Indicators and model features
│   ├── __init__.py
│   ├── feature_service.py
│   ├── indicators/
│   │   ├── moving_average.py
│   │   ├── rsi.py
│   │   └── ...
│   ├── transforms/
│   │   ├── normalize.py
│   │   └── encode.py
│   ├── utils/
│   └── main.py
│
├── strategy_engine/            # Microservice 3: Rule-based and ML strategies
│   ├── __init__.py
│   ├── strategy_service.py
│   ├── config.py
│   ├── strategies/
│   │   ├── ma_crossover.py
│   │   ├── mean_reversion.py
│   ├── signals/
│   │   ├── signal_model.py
│   │   └── signal_utils.py
│   ├── utils/
│   └── main.py
│
├── risk_management/            # Microservice 4: Risk checks and position sizing
│   ├── __init__.py
│   ├── risk_service.py
│   ├── rules/
│   │   ├── stop_loss.py
│   │   ├── max_exposure.py
│   ├── utils/
│   └── main.py
│
├── order_execution/            # Microservice 5: Broker API and execution tracking
│   ├── __init__.py
│   ├── execution_service.py
│   ├── broker/
│   │   ├── ibkr.py
│   │   ├── mock_broker.py
│   ├── utils/
│   └── main.py
│
├── alerts/                     # Microservice 6: Real-time notifications
│   ├── __init__.py
│   ├── alert_service.py
│   ├── channels/
│   │   ├── email.py
│   │   ├── sms.py
│   └── main.py
│
├── monitoring/                 # Microservice 7: Logging, system health, audits
│   ├── __init__.py
│   ├── logger.py
│   ├── health_check.py
│   └── main.py
│
├── backtester/                 # Microservice 8: Simulate strategy performance
│   ├── __init__.py
│   ├── backtest_engine.py
│   ├── metrics.py
│   ├── portfolio_tracker.py
│   └── main.py
│
├── shared/                     # Shared models, enums, utils across services
│   ├── schemas/
│   │   ├── signal.py
│   │   ├── order.py
│   │   └── data_point.py
│   ├── enums.py
│   ├── constants.py
│   └── utils.py
│
└── run_pipeline.py             # Orchestrator script to link everything together

