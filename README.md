## The issues
- Cache didn't discriminate between tenants
- Database pool was using incorrect credentials
- Database pool was using incorrect class(`poolclass=QueuePool` -> `AsyncAdaptedQueuePool`)
- `get_session` returned a coroutine instead of an async context manager
- Property names were hardcoded in frontend
- Revenue calculation didn't take the timezone into account. Even though the
  function's not used now, could lead to bugs in the future, so noted and fixed
  it.
- Decimals were dropped when serving to frontend.
