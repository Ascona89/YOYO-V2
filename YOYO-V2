import streamlit as st
from supabase import create_client

# Verbindung zu Supabase
try:
    supabase = create_client(
        st.secrets["SUPABASE_URL"],
        st.secrets["SUPABASE_KEY"]
    )
    # Test: Tabelle "login_events" abrufen (falls existiert)
    data = supabase.table("login_events").select("*").limit(1).execute()
    st.success("✅ Supabase Verbindung erfolgreich!")
    st.write("Beispiel-Daten aus login_events:", data.data)
except Exception as e:
    st.error(f"❌ Supabase Verbindung fehlgeschlagen: {e}")
